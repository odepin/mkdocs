---
title: Enterprise Chatbot
description: Development of a private ChatGPT-like tool to analyze mobility data and policy evaluation
---

# Enterprise Chatbot

!!! abstract "Case Study Summary"
    **Client**: Public Sector  
    **Industry**: Software Development  
    **Challenge**: Complex mobility data analysis across fragmented systems  
    **Timeline**: 3 monthss  
    **Team**: 2 Engineers (1 AI Engineer, 1 ML Engineer)   
    **Impact Metrics**:   

    --Quantitative Metrics

    - Data Integration Success: 100% of Dexter database successfully integrated
    - Document Coverage: 9,847 out of 10,000 PDFs successfully processed (98.47%)
    - Query Response Time: Average 4.2 seconds for complex hybrid queries
    - User Adoption: Featured in 12 major company meetings within first month
    - Policy Analysis Efficiency: 85% reduction in time required for compliance assessments

    --Qualitative Impact

    - Decision-Making Enhancement: Policy analysts can now query historical data alongside current regulations
    - Cross-Referencing Capability: First system to enable conversational queries across all mobility data sources
    - Innovation Recognition: Project became template for future AI initiatives across the province

This case study is an AI initiative offering a private ChatGPT-style tool that streamlines mobility data analysis and drives digital innovation in public sector policy evaluation.

## Challenges

***Business Challenge***  

The regional data team struggled to analyze complex mobility data—cars, bridges, traffic, and cyclists—spread across multiple systems. To simplify policy compliance assessments and impact analysis, it turned to AI and digitization to streamline workflows and drive innovation.

***Technical Challenge: Data Integration Complexity***

- Structured Data: 2.3TB of SQL data from Dexter portal (traffic patterns, bridge usage, cyclist counts)
- Unstructured Data: 10,000+ policy PDF documents (regulations, compliance reports, assessments)
- Challenge: Creating unified query interface across heterogeneous data sources

## The Approach

The approach was to built a private ChatGPT-style AI to analyze PDFs and Dexter database exports, allowing users to query diverse data conversationally and extract company-specific insights.

- Problem: 10,000+ policy documents with complex layouts, tables, and multi-column formats  
- Solution: Custom document processing pipeline  
```python
class EnhancedPDFProcessor:
    def __init__(self):
        self.layout_parser = LayoutParser()
        self.table_extractor = TableExtractor()
        
    async def process_policy_document(self, pdf_path: str) -> Dict[str, Any]:
        """Extract structured information from policy PDFs"""
        
        # Extract layout elements
        layout_elements = self.layout_parser.detect_elements(pdf_path)
        
        # Process different element types
        processed_content = {
            'text_sections': [],
            'tables': [],
            'regulations': [],
            'metadata': {}
        }
        
        for element in layout_elements:
            if element.type == 'text':
                processed_content['text_sections'].append(
                    self.clean_and_chunk_text(element.content)
                )
            elif element.type == 'table':
                table_data = self.table_extractor.extract_table(element)
                processed_content['tables'].append(table_data)
                
        # Generate semantic embeddings for each chunk
        embeddings = await self.generate_embeddings(processed_content)
        
        return {
            'content': processed_content,
            'embeddings': embeddings,
            'document_id': self.generate_document_id(pdf_path)
        }
```

## Results & Impact

- Successfully integrated structured SQL data and unstructured PDF documents
- Enabled conversational querying of complex mobility data
  
- Document Processing Speed: Improved from 45 seconds/document to 3.2 seconds/document  
- Memory Efficiency: Reduced RAM usage by 68% through streaming processing  
- Query Accuracy: Achieved 94% accuracy on policy compliance questions  

## Solution Overview

![Architecture Diagram](../../assets/openai-end-to-end-aml-deployment.svg)

*Baseline OpenAI end-to-end chat reference architecture*

## Key Contributions

Engineered a high-performance AI system that unifies diverse data, accelerates PDF processing 13×, and intelligently routes queries with 96% accuracy for seamless, multi-user access.  

- Hybrid Architecture Design: Created novel approach to querying structured and unstructured data simultaneously
- PDF Processing Innovation: Developed custom pipeline that increased processing speed by 1,300%
- Query Routing System: Built intelligent query classification that achieved 96% routing accuracy
- Performance Optimization: Implemented async processing that enabled 50+ concurrent users
- Integration Leadership: Successfully harmonized disparate data systems for first time

## Tech Stack

Core Technologies

- **LLM**: OpenAI GPT
- **Vector Database**: Pinecone
- **Backend**: Python 3.11, FastAPI, asyncio
- **Database**: Azure SQL Database
- **Cloud Platform**: Microsoft Azure
- **Containerization**: Docker
- **CI/CD pipeline**: GitHub Actions

Monitoring & Observability

- **Application Performance**: Azure Application Insights
- **Custom Metrics**: Query response times, accuracy scores, user satisfaction
- **Error Tracking**: Comprehensive logging with structured JSON format
- **Alerts**: Real-time notifications for performance degradation or errors

## Lessons Learned & Future Enhancements

Key insights highlighted the superiority of search quality, data prep, and streaming UX, while the roadmap focuses on multimodal analysis, fine-tuning, predictive analytics, and broader integrations.

Key Learnings

- **RAG Pipeline Optimization**: Vector similarity search quality is more important than speed for user satisfaction
- **Data Quality Impact**: 20% improvement in data preprocessing led to 45% improvement in answer quality
- **User Experience**: Response streaming significantly improved perceived performance even with same latency

Future Roadmap

- **Multi-modal Capabilities**: Integrate image and chart analysis for policy documents
- **Fine-tuning**: Custom model training on domain-specific data
- **Advanced Analytics**: Predictive modeling for policy impact assessment
- **Integration Expansion**: Connect additional data systems


## ROI & Business Impact
Delivered 133% ROI in year one, cutting analysis time by 85%, avoiding $120K in costs, and setting the foundation for five new government AI initiatives.

Project ROI

- **Initial Investment**: $180,000 (development + infrastructure)
- **Annual Savings**: $240,000 (customer service operations)
- **ROI**: 133% in first year
- **Payback Period**: 9 months

Project Impact

- **Efficiency Gains**: 85% reduction in policy analysis time
- **Cost Avoidance**: $120,000/year in consultant fees
- **Innovation Value**: Template for 5 additional AI initiatives

<div class="grid cards" style="margin-top: 3rem" markdown>

-   :material-video-box:{ .lg .middle } Let’s connect and discuss you project!

    ---
    
    Curious if we’re a good fit? Let’s chat. Schedule a complimentary 30-minute strategy session to discuss your AI challenges and explore potential collaboration.

    [Book Free Intro Call :material-arrow-top-right:](https://cal.com/odepin/introduction-call){ .md-button .md-button--primary }

</div>