# **PDF RAG Assistant (Chatbot hỏi đáp tài liệu)**
Dự án này xây dựng một chatbot hỏi đáp tài liệu PDF bằng tiếng Việt dựa trên kiến trúc **Retrieval-Augmented Generation (RAG)**. Hệ thống cho phép người dùng upload file PDF và đặt câu hỏi trực tiếp về nội dung tài liệu, chatbot sẽ truy xuất thông tin liên quan và sinh câu trả lời chính xác dựa trên nội dung đó.

## **Công nghệ sử dụng**
- **LangChain**: Xây dựng pipeline RAG
- **ChromaDB**: Lưu trữ vector embeddings
- **HuggingFace Transformers**:
  - Embedding: bkai-foundation-models/vietnamese-bi-encoder
  - LLM: lmsys/vicuna-7b-v1.5 (quantization 4-bit)
- **Semantic Chunking**: Chia tài liệu theo ngữ nghĩa
- **Streamlit**: Xây dựng giao diện web tương tác
- **PyPDF**: Đọc và xử lý file PDF

## **Quy trình hoạt động**
1. Người dùng upload file PDF
2. Hệ thống đọc nội dung PDF và chia nhỏ văn bản bằng Semantic Chunker
3. Các đoạn văn được chuyển thành vector embeddings và lưu vào vector database
4. Khi người dùng đặt câu hỏi:
    - Retriever tìm các đoạn văn liên quan
    - LLM (Vicuna) sinh câu trả lời dựa trên context truy xuất
5. Kết quả được hiển thị trực tiếp trên giao diện chat

## **Giao diện**
- Upload PDF
- Xử lý tài liệu (tạo vector database)
- Hỏi đáp liên tục mà không cần xử lý lại PDF
- Hỗ trợ mở rộng thành chatbot nhiều lượt hội thoại

## **Mục tiêu dự án**
- Hiểu và triển khai kiến trúc RAG
- Ứng dụng LLM vào bài toán hỏi đáp tài liệu thực tế
- Xây dựng chatbot AI tiếng Việt có khả năng mở rộng
