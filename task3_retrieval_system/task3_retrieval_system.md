Task 3 – Content-Based Image Retrieval (CBIR)
Objective

Build a retrieval system that finds visually similar chest X-ray images using learned embeddings.

Embedding Model

ResNet18 trained on PneumoniaMNIST

Final classification layer removed

512-dimensional embeddings extracted

These embeddings capture medically relevant visual features.

Vector Index

Library used: FAISS
Index type: L2 (Euclidean distance)

All 624 test embeddings were indexed for nearest-neighbor search.

Retrieval Interface

Implemented:

Image-to-image retrieval

Given a query image:

Extract embedding

Search FAISS index

Return top-k similar images

Evaluation

Metric: Precision@k

Precision@5 ≈ 0.91

This indicates strong clustering of similar medical cases.

Observations

Pneumonia cases grouped together effectively.

Normal cases also clustered correctly.

Retrieval quality reflects strong embedding separability.

Limitations

Binary dataset simplifies clustering.

Low-resolution images limit fine-grained similarity.

Text-to-image retrieval not implemented.

Conclusion

The CBIR system successfully demonstrates medical embedding extraction and vector-based similarity search.
