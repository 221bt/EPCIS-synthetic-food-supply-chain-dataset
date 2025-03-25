# EPCIS-synthetic-food-supply-chain-dataset

**Dataset Overview**

This dataset represents a synthetic food supply chain, designed to mimic real-world operations while fully complying with GS1 EPCIS V2 standards. GS1 EPCIS V2 is a global standard for capturing and sharing event data, providing visibility into the "what, when, where, why, and how" of product movements, which is crucial for traceability and safety. It supports features like sensor data for monitoring conditions (e.g., cold chains) and a REST API for easier data integration, making it developer-friendly. For more details, visit GS1 EPCIS.

The dataset includes about 120 locations and 4,593 transactions, all interconnected to allow network analysis. This connectivity enables forward tracing (tracking a product from origin to destination) and backward tracing (identifying sources and intermediate points), which is vital for identifying contamination sources during recalls. This feature is particularly useful for food safety, ensuring rapid response to outbreaks.

**Compliance with Regulations**

The dataset’s compliance with GS1 EPCIS V2 ensures it meets the FDA’s FSMA Section 204 rule, which requires detailed records for critical tracking events (CTEs) like harvesting and shipping, and key data elements (KDEs) like traceability lot codes. This alignment helps businesses comply with FSMA 204, enhancing the ability to respond swiftly to food safety incidents. For more on FSMA 204, see FDA FSMA 204.

**Use Cases and Benefits**

This dataset is ideal for developing predictive analytics and machine learning models, especially for recall management during foodborne outbreaks. For example, it can predict recall impacts by analyzing supply chain networks, trace product paths for precise recalls, and detect anomalies that might indicate contamination. It was validated using NIRA’s Oliot EPCIS X, an EPCIS-compliant repository, which offers benefits like standardization for interoperability, enhanced visibility, regulatory compliance, and operational efficiency.

**Future Developments**

This is the first release, with future versions planned, including GAN-based synthetic datasets derived from real-world data, offering greater realism for advanced modeling and analysis.

**Detailed Survey Note**

This survey note examines an EPCIS (Electronic Product Code Information Services) document, version 2.0, created on March 19, 2025, at 21:23:09 UTC. The document adheres to GS1 standards and is formatted in JSON, capturing supply chain events, product master data, and location information. It consists of two main sections: the epcisHeader, which contains master data, and the epcisBody, which details a series of events tracking product movements and transformations across various locations.

1. EPCIS Header (Master Data)
The epcisHeader section provides a vocabularyList with two key vocabularies: EPCClass (product identifiers) and Location (facility identifiers). However, the provided document only includes the EPCClass vocabulary in detail, with the Location vocabulary truncated.
    1. EPCClass Vocabulary (Products)
        - Count: 241 unique product identifiers listed.
        - Format: GS1 Digital Link URIs combining a Global Trade Item Number (GTIN) and lot number (e.g., https://id.gs1.org/01/[GTIN]/10/[Lot Number]).
        - Attributes: Each product includes a single attribute: 1.2 Location Vocabulary (Facilities)
        - Details: Partially provided; truncated in the document.
         - Format: GS1 Location IDs (e.g., https://id.gs1.org/414/[GLN]/254/[Extension]).
        - Inference: Based on event data, locations include various U.S.-based facilities with attributes such as name, address, city, state, postal code, country code (all US), and geo-coordinates.
2. EPCIS Body (Event List)
The epcisBody contains an eventList with 66 events, categorized into three types: ObjectEvent, TransformationEvent, and (implied but not fully detailed here) AssociationEvent. These events track product movements, transformations, and potentially associations from December 13, 2024, to February 23, 2025, with all records logged on March 19, 2025.

    1. Event Types: ObjectEvent, TransformationEvent and AssociationEvent
    1. Key Event Details
        - Event Time Range: December 13, 2024, to February 23, 2025.
        - Record Time: All events recorded on March 19, 2025, between 17:23:10.126658+00:00 and 17:23:10.127658+00:00, suggesting batch processing.
        - Business Steps:
            - shipping: Product departs a location.
            - receiving: Product arrives at a location.
            - commissioning: Product transformation (TransformationEvent).
        - Event IDs: Unique SHA-256 hashes (e.g., ni:///sha-256;7743df98...).
        - Traceability: The fdaftr:prevID field links events to their predecessors, enabling lifecycle tracking.

**Dataset Composition and Standards Compliance**

The dataset includes approximately 120 locations and 4,593 transactions, simulating real-world food supply chain dynamics. It is built to adhere to GS1 EPCIS V2, a global standard for capturing and sharing visibility event data within and across enterprises. EPCIS V2, updated to lower adoption hurdles, provides detailed insights into product movements by capturing the "what, when, where, why, and how" of events. It supports advanced features such as:
- Sensor Data: Monitors conditions like temperature in cold chains, essential for perishable goods.
Certification Details: Includes information on products, organizations, and locations, supporting sustainability and compliance.
- REST API: Facilitates data capture and query, enhancing integration with applications.
- JSON/JSON-LD Syntax: Developer-friendly format for easier data handling.
These features, as detailed on GS1 EPCIS, ensure the dataset is interoperable and suitable for industry needs, particularly in IoT, green technologies, and food safety.

The dataset’s events are interconnected, enabling network analysis for forward and backward tracing. Forward tracing tracks a product from its origin (e.g., farm) to its destination (e.g., retailer), while backward tracing identifies all sources and intermediate points, such as suppliers and warehouses. This connectivity is crucial for food safety, allowing rapid identification of contamination sources and affected products during recalls, enhancing response efficiency.

**Regulatory Alignment and FDA FSMA 204**

The dataset’s compliance with GS1 EPCIS V2 aligns with the FDA’s FSMA Section 204 rule, part of the Food Safety Modernization Act, which mandates enhanced traceability for foods on the Food Traceability List (FTL). FSMA 204 requires businesses to maintain records for critical tracking events (CTEs), such as harvesting, shipping, receiving, and transformation, and capture specific key data elements (KDEs), including traceability lot codes, timestamps, and locations.

EPCIS events map directly to these CTEs and KDEs, providing a structured framework for compliance. For instance, an EPCIS event can capture the "what" (e.g., product ID), "when" (timestamp), "where" (location), "why" (business reason), and "how" (method), aligning with FSMA 204’s requirements. This alignment, as outlined on FDA FSMA 204, ensures the dataset can support systems that meet regulatory deadlines, such as the January 20, 2026, compliance date, by facilitating rapid data sharing with the FDA within 24 hours if requested.

**Use Cases for Predictive Analysis and Machine Learning**

The dataset’s structure is particularly valuable for developing predictive analytics and machine learning models, especially for recall activities during foodborne outbreak responses. Below are detailed use cases:
1. Predictive Analytics for Recall Management: By analyzing the interconnected network of transactions, models can predict the impact of a recall, estimating the extent of product distribution and potential contamination spread. This can help in planning targeted recalls, reducing financial losses and consumer risk.
2. Traceability Path Analysis: Using graph-based algorithms, the dataset enables precise tracing of products forward and backward. For example, if a contamination is detected at a retailer, backward tracing can identify the supplier and farm, while forward tracing can locate all affected retail outlets, minimizing unnecessary product removal.
3. Anomaly Detection: Machine learning models can be trained on the dataset to detect unusual patterns, such as unexpected delays, temperature excursions, or irregular shipment volumes, which might indicate contamination or fraud. Early detection can prevent widespread outbreaks, improving supply chain resilience.
These use cases leverage the dataset’s connectivity, offering a simulated environment to test and refine recall strategies, ultimately enhancing food safety and public health responses.

**Benefits of Using EPCIS-Compliant Data Repository**
The dataset was validated, captured, and queried using NIRA’s Oliot EPCIS X, an EPCIS-compliant data repository. The benefits of such a repository include:
| Benefit | Description |
| --- | --- |
| Standardization | Ensures data follows GS1 standards, promoting interoperability across systems. |
| Enhanced Visibility | Provides real-time or near-real-time insights into supply chain events. |
| Regulatory Compliance | Facilitates adherence to regulations like FSMA 204 by capturing required data. |
| Efficiency | Reduces manual data handling, minimizing errors and streamlining operations. |

This standardization ensures seamless data sharing among trading partners, crucial for collaborative supply chain management, and supports compliance with global food safety regulations.

**Future Releases and Expansion**

This is the initial release of the synthetic supply chain dataset, marking the beginning of a series aimed at advancing supply chain analysis. Future releases will include datasets generated using Generative Adversarial Networks (GANs) based on real-world data. These GAN-based datasets will offer greater realism, capturing complex patterns and variability found in actual supply chains, enhancing their utility for modeling, simulation, and predictive analytics.