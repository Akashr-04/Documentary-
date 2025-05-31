# Document Intelligence Platform

A modern web application that allows users to upload documents and ask natural language questions about their content using RAG (Retrieval Augmented Generation) technology.

![Uploading Screenshot 2025-05-31 212019.png…]()


## Features

- 📄 Document upload and management
- 💬 Natural language question answering
- 🔍 Intelligent document search
- 📊 Document metadata visualization
- 🔗 Source citations for answers
- 📱 Responsive design for all devices

## Setup Instructions

1. Clone the repository:
```bash
git clone https://github.com/yourusername/document-intelligence-platform.git
cd document-intelligence-platform
```

2. Install dependencies:
```bash
npm install
```

3. Start the development server:
```bash
npm run dev
```

4. Open your browser and navigate to the local server URL

## API Documentation

### Documents API

#### GET /api/documents/
Retrieves all documents.

Response:
```json
[
  {
    "id": "1",
    "title": "Annual Report 2024",
    "filePath": "/documents/annual-report-2024.txt",
    "fileType": "txt",
    "fileSize": 256000,
    "pageCount": 25,
    "status": "completed",
    "createdAt": "2024-05-20T10:30:00Z",
    "updatedAt": "2024-05-20T10:35:00Z"
  }
]
```

#### POST /api/documents/upload/
Upload a new document.

Request:
- Content-Type: multipart/form-data
- Body: file (File)

Response:
```json
{
  "id": "123",
  "title": "Document Title",
  "status": "processing"
}
```

### Q&A API

#### POST /api/documents/{documentId}/ask/
Ask a question about a document.

Request:
```json
{
  "question": "What were the key findings?",
  "num_chunks": 3
}
```

Response:
```json
{
  "id": "qa_123",
  "answer": "The key findings were...",
  "sources": [
    {
      "chunkId": "1",
      "content": "Relevant text from document",
      "pageNumbers": [3],
      "relevanceScore": 0.92
    }
  ]
}
```

## Sample Questions and Answers

### Annual Report Analysis
Q: "What was the company's revenue growth in 2024?"
A: "According to the annual report, the company achieved a 15% year-over-year revenue growth in 2024, reaching $2.5 billion in total revenue. This growth was primarily driven by expansion in the Asian market and new product launches."

Sources:
- Page 12: "Revenue grew 15% YoY to $2.5B"
- Page 13: "Asian market expansion contributed 60% of growth"

### Product Specification
Q: "What are the main technical requirements?"
A: "The product requires a minimum of 8GB RAM, 100GB storage, and supports Windows 10/11 and macOS 12+. Key features include real-time data processing capabilities and integration with standard industry protocols."

Sources:
- Page 3: "System Requirements: 8GB RAM, 100GB storage"
- Page 4: "OS Support: Windows 10/11, macOS 12+"


## Tech Stack

- Frontend: React with TypeScript
- Styling: Tailwind CSS
- Icons: Lucide React
- File Upload: React Dropzone
- Routing: React Router
- HTTP Client: Axios

## Development

To start development:

1. Run the development server:
```bash
npm run dev
```

2. Start making changes to the code
3. The development server will automatically reload when you save changes

## Building for Production

To create a production build:

```bash
npm run build
```

The build output will be in the `dist` directory.
