#cybersecurity-concepts 
## Collection
- which devices will we collect events from?
- Which events do we want to collect
- How long will we retain the logs?
- Where will we store the logs?
	- How do we secure these logs?
- Methods of collection
	- Agents
	- Agentless
## Aggregation
- Collecting and consolidating events
- Unify the timeline across the organization
- Enhancing holistic visibility
- Allows for correlation and analysis
## Parsing and Normalization
- Ensure consistency across logs
- Extracting structured information
	- Fields, columns
	- Regular expressions, parsing tools, or custom parsers
- Convert into a common schema
	- Field Mapping
	- Data Transformation
	- Common Event Format
## Retention
- Storing log data to ensure analysis availability
	- incident response
	- compliance
- Log retention policies
	- retention period
	- storage solutions
	- security controls
	- storage integrity 
	- Data destruction
## Indexing
- Turns raw logs into searchable events data
- repository or grouping of events
- efficient log retrieval
- helps with scaling as log sources grow
## Correlation and Analysis
- Linking related log events together
- contextualization
	- enriching events with additional metadata
- Correlation Rules
	- specify how events should be correlated
- Correlation Engines
- Analysis
	- Pattern Recognition
	- Anomaly Detection
## Alerting
- Notify relevant people about security incidents
- Threshold-Based Alerts
- Pattern-Based Alerts
- Anomaly-Based Alerts
- Event-Based Alerts