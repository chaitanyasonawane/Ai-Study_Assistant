from langchain.schema import BaseRetriever
from typing import List
from langchain.docstore.document import Document

class SimpleRetriever(BaseRetriever):
    def __init__(self, texts):
        self.texts = texts
        self.contents = [t.page_content for t in texts]

        from sklearn.feature_extraction.text import TfidfVectorizer
        import numpy as np

        self.vectorizer = TfidfVectorizer()
        self.vectors = self.vectorizer.fit_transform(self.contents)
        self.np = np

    def _get_relevant_documents(self, query: str) -> List[Document]:
        query_vec = self.vectorizer.transform([query])
        scores = (self.vectors @ query_vec.T).toarray().flatten()

        top_k_idx = self.np.argsort(scores)[-3:][::-1]
        return [self.texts[i] for i in top_k_idx]

    async def _aget_relevant_documents(self, query: str):
        return self._get_relevant_documents(query)
