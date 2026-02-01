# design.md  
## Project: SmritiSetu – A Bridge Between Generations


## 1. System Architecture Overview

SmritiSetu is designed as a cloud-native, AI-driven system that captures unstructured oral narratives and transforms them into structured, searchable knowledge artifacts. The architecture emphasizes scalability, reliability, ethical data handling, and accessibility for non-literate users.

The system follows a modular, serverless design to efficiently process voice-based inputs and enable long-term preservation of cultural knowledge.


## 2. High-Level Architecture

The system architecture is divided into the following layers:

- Data Ingestion Layer  
- Speech Processing Layer  
- AI Knowledge Processing Layer  
- Storage and Indexing Layer  
- Application and Access Layer  

Each layer operates independently to ensure maintainability and scalability.


## 3. Component Description

### 3.1 Data Ingestion Layer
Users record oral narratives using a web or mobile interface. Audio files are captured in common formats and securely uploaded to cloud storage.

Technologies:
- Frontend Interface (Web/Mobile – Conceptual)
- Amazon S3 for audio storage


### 3.2 Speech Processing Layer
Recorded audio is converted into textual transcripts using AI-powered speech recognition services capable of handling multiple Indian languages.

Technologies:
- Amazon Transcribe


### 3.3 AI Knowledge Processing Layer
Transcribed text is processed using large language models to extract semantic meaning, identify themes, summarize narratives, and generate structured knowledge representations.

Technologies:
- Amazon Bedrock


### 3.4 Storage and Indexing Layer
Structured knowledge, transcripts, metadata, and references to audio files are stored in a highly available and scalable data store. Metadata enables efficient indexing and retrieval.

Technologies:
- Amazon DynamoDB
- Amazon S3


### 3.5 Knowledge Retrieval and Search
Users can explore preserved knowledge using semantic search capabilities that allow discovery by topic, region, or cultural theme rather than exact keyword matches.

Technologies:
- Amazon Q


### 3.6 Application and Access Layer
Provides interfaces for content submission, browsing, and search while enforcing access control and role-based permissions.

Technologies:
- AWS Lambda
- API Gateway (Conceptual)


## 4. Data Flow Description

1. A user records an oral narrative using the application interface.
2. The audio file is uploaded and stored in Amazon S3.
3. Amazon Transcribe converts the audio into a text transcript.
4. The transcript is sent to Amazon Bedrock for semantic analysis.
5. Structured knowledge and metadata are generated.
6. Data is stored in Amazon DynamoDB with references to audio files in S3.
7. Users retrieve knowledge through Amazon Q-powered semantic search.


## 5. Technology Stack Summary

1. Voice Capture:
Web or mobile-based interface (conceptual) used for recording oral narratives.

2. Speech-to-Text Processing:
Amazon Transcribe is used to convert recorded speech into textual transcripts in supported regional languages.

3. AI Knowledge Processing:
Amazon Bedrock is utilized to analyze transcripts, extract semantic meaning, identify themes, and generate structured knowledge representations.

4. Storage Layer:
Amazon S3 is used for durable storage of audio files and transcript data.

5. Metadata Management:
Amazon DynamoDB stores structured knowledge artifacts and associated metadata for efficient indexing.

6. Search and Retrieval:
Amazon Q enables semantic search and knowledge discovery across preserved content.

7. Backend Processing:
AWS Lambda handles backend orchestration and processing logic in a serverless manner.


## 6. Scalability and Reliability

- Serverless services ensure automatic scaling based on demand.
- Distributed storage provides high availability and durability.
- Modular architecture allows independent scaling of processing components.


## 7. Security and Privacy Design

- Secure storage of audio and text data.
- Role-based access control for users and administrators.
- Consent metadata attached to each narrative.
- Encryption at rest and in transit (conceptual design).


## 8. Ethical Design Considerations

- Cultural ownership is retained by contributing communities.
- The system avoids commercial exploitation of preserved knowledge.
- AI processing focuses on preservation, not content alteration.
- Transparent data usage policies are enforced.


## 9. Limitations and Risks

- Speech recognition accuracy may vary across dialects.
- Limited availability of training data for low-resource languages.
- Dependency on internet connectivity in rural regions.


## 10. Future Enhancements

- Offline voice capture with delayed synchronization.
- Support for additional dialects and minority languages.
- Community-led moderation and validation mechanisms.
- Integration with educational and digital museum platforms.