---
name: monitoring-observability
description: Prometheus, Grafana, CloudWatch, Azure Monitor, Stackdriver, logging, alerting, and SRE practices
---

# Monitoring and Observability

## Prometheus and Grafana Setup

### Prometheus
- **Core Concepts**
  - Time-series database for metrics
  - Pull-based metrics collection
  - PromQL query language
  - Alerting rules and notifications

- **Best Practices**
  - Use appropriate metric types (Counter, Gauge, Histogram, Summary)
  - Label metrics with relevant dimensions
  - Use metric naming conventions
  - Implement relabeling for metric filtering
  - Use federation for multi-cluster setups

- **Configuration**
  - Configure scrape targets for services
  - Use service discovery for dynamic targets
  - Configure retention policies
  - Implement remote write for long-term storage
  - Use alert rules for proactive monitoring

- **PromQL Examples**
  ```promql
  # CPU usage rate
  rate(process_cpu_seconds_total[5m])
  
  # Request error rate
  rate(http_requests_total{status=~"5.."}[5m]) / rate(http_requests_total[5m])
  
  # P95 latency
  histogram_quantile(0.95, rate(http_request_duration_seconds_bucket[5m]))
  
  # Memory usage
  process_resident_memory_bytes / node_memory_MemTotal_bytes * 100
  ```

### Grafana
- **Core Concepts**
  - Visualization and dashboard platform
  - Multiple data source support
  - Alerting and notifications
  - Plugin ecosystem

- **Best Practices**
  - Use folder organization for dashboards
  - Use dashboard variables for interactivity
  - Implement dashboard versioning
  - Use annotations for event marking
  - Share dashboards via JSON export

- **Dashboard Design**
  - Create role-specific dashboards (SRE, developer, business)
  - Use appropriate visualization types (graph, gauge, table, stat)
  - Implement drill-down capabilities
  - Use consistent color schemes
  - Include context and descriptions

- **Alerting**
  - Configure alert rules in Grafana
  - Use notification channels (email, Slack, PagerDuty)
  - Implement alert grouping and routing
  - Use alert templates for clear messages
  - Configure alert silencing and downtime

## CloudWatch (AWS) Monitoring

### Core Concepts
- **Metrics**: Time-series data points
- **Dashboards**: Visualizations of metrics
- **Alarms**: Threshold-based alerts
- **Logs**: Log data collection and analysis
- **Events**: Event-driven monitoring

### Best Practices
- **Metric Collection**
  - Use custom metrics for application-specific data
  - Use metric filters for log-based metrics
  - Use metric dimensions for filtering
  - Implement metric aggregation
  - Use metric streams for real-time processing

- **Dashboard Design**
  - Create service-specific dashboards
  - Use widgets for different visualizations
  - Implement dashboard variables
  - Use cross-account dashboards
  - Share dashboards with teams

- **Alarm Configuration**
  - Use appropriate alarm thresholds
  - Implement alarm actions (SNS, Auto Scaling, EC2 actions)
  - Use composite alarms for complex conditions
  - Configure alarm states and transitions
  - Use alarm tags for organization

### CloudWatch Logs
- **Log Groups**: Logical containers for logs
- **Log Streams**: Sequences of log events
- **Metric Filters**: Extract metrics from logs
- **Subscription Filters**: Stream logs to other services
- **Insights**: Query and analyze logs

### CloudWatch Examples
```json
// Alarm configuration
{
  "AlarmName": "HighCPUUsage",
  "MetricName": "CPUUtilization",
  "Namespace": "AWS/EC2",
  "Statistic": "Average",
  "Period": 300,
  "EvaluationPeriods": 2,
  "Threshold": 80,
  "ComparisonOperator": "GreaterThanThreshold"
}

// Metric filter
{
  "filterPattern": "[timestamp, request_id, status_code, latency]",
  "metricTransformations": [
    {
      "metricName": "RequestLatency",
      "metricNamespace": "Application",
      "metricValue": "$latency"
    }
  ]
}
```

## Azure Monitor

### Core Concepts
- **Metrics**: Time-series data
- **Logs**: Log data collection and analysis
- **Alerts**: Threshold-based alerts
- **Dashboards**: Visualizations
- **Application Insights**: Application monitoring

### Best Practices
- **Metric Collection**
  - Use custom metrics for application data
  - Use metric dimensions for filtering
  - Implement metric aggregation
  - Use metric alerts for proactive monitoring
  - Configure metric collection rules

- **Log Analytics**
  - Use Kusto Query Language (KQL) for log queries
  - Create custom log tables
  - Implement log collection rules
  - Use log alerts for monitoring
  - Configure log retention policies

- **Application Insights**
  - Enable distributed tracing
  - Use custom telemetry
  - Implement dependency tracking
  - Configure performance counters
  - Use smart detection for anomalies

### Azure Monitor Examples
```kql
// KQL query for error rate
requests
| where timestamp > ago(1h)
| summarize count() by success
| project error_rate = 100.0 * (count_ - count_success) / count_

// Query for slow requests
requests
| where timestamp > ago(1h)
| where duration > 1000
| summarize count() by name
| top 10 by count_

// Query for exceptions
exceptions
| where timestamp > ago(1h)
| summarize count() by type, problemId
| top 10 by count_
```

## Stackdriver (GCP) Monitoring

### Core Concepts
- **Metrics**: Time-series data
- **Dashboards**: Visualizations
- **Alerting**: Threshold-based alerts
- **Logging**: Log data collection
- **Tracing**: Distributed tracing

### Best Practices
- **Metric Collection**
  - Use custom metrics for application data
  - Use metric labels for filtering
  - Implement metric aggregation
  - Use metric-based alerting policies
  - Configure metric descriptors

- **Dashboard Design**
  - Create service-specific dashboards
  - Use dashboard variables
  - Implement dashboard sharing
  - Use dashboard templates
  - Configure dashboard refresh intervals

- **Logging**
  - Use log sinks for log routing
  - Implement log-based metrics
  - Configure log exclusions
  - Use log alerts for monitoring
  - Configure log retention

### Stackdriver Examples
```yaml
# Alerting policy
displayName: "High Error Rate"
conditions:
  - displayName: "Error rate > 5%"
    conditionThreshold:
      filter: 'metric.type="custom.googleapis.com/error_rate"'
      comparison: COMPARISON_GT
      thresholdValue: 0.05
      duration: 300s
      aggregations:
        - alignmentPeriod: 60s
          perSeriesAligner: ALIGN_RATE
```

## Logging and Log Aggregation

### ELK Stack (Elasticsearch, Logstash, Kibana)
- **Elasticsearch**: Search and analytics engine
- **Logstash**: Data processing pipeline
- **Kibana**: Visualization platform
- **Beats**: Data shippers

### Best Practices
- **Log Collection**
  - Use centralized logging
  - Implement log shippers (Filebeat, Fluentd, Logstash)
  - Use log parsing and normalization
  - Configure log retention policies
  - Implement log archiving

- **Log Analysis**
  - Use index patterns for organization
  - Implement log queries and filters
  - Use saved searches for common queries
  - Create visualizations for log data
  - Use dashboards for log monitoring

- **Log Security**
  - Implement log encryption at rest
  - Use secure log transmission (TLS)
  - Implement log access controls
  - Configure log audit trails
  - Use log redaction for sensitive data

### Loki
- **Core Concepts**
  - Lightweight log aggregation system
  - Label-based indexing
  - Grafana integration
  - PromQL-like query language (LogQL)

- **Best Practices**
  - Use appropriate log labels
  - Implement log retention policies
  - Use log streams for organization
  - Configure log scraping
  - Implement log alerting

## Alerting Strategies and Incident Response

### Alerting Best Practices
- **Alert Design**
  - Use meaningful alert names and descriptions
  - Include relevant context in alerts
  - Use appropriate severity levels
  - Configure alert thresholds carefully
  - Implement alert deduplication

- **Alert Routing**
  - Route alerts to appropriate teams
  - Use escalation policies
  - Configure on-call rotations
  - Implement alert grouping
  - Use notification channels (email, Slack, PagerDuty)

- **Alert Quality**
  - Reduce alert noise with proper filtering
  - Implement alert suppression
  - Use alert correlation
  - Configure alert cooldown periods
  - Implement alert auto-resolution

### Incident Response
- **Incident Lifecycle**
  - Detection: Identify incident
  - Triage: Assess severity and impact
  - Response: Mitigate incident
  - Resolution: Restore service
  - Post-Mortem: Learn and improve

- **Best Practices**
  - Use incident severity levels
  - Implement incident communication
  - Use runbooks for common incidents
  - Conduct post-mortems
  - Implement follow-up actions

- **Runbooks**
  - Document common incident scenarios
  - Include step-by-step procedures
  - Include relevant commands and tools
  - Update runbooks based on incidents
  - Share runbooks with teams

## SLO/SLI Definitions and Tracking

### SLI (Service Level Indicator)
- **Definition**: Quantitative measure of service performance
- **Common SLIs**:
  - Availability: Percentage of time service is operational
  - Latency: Response time for requests
  - Error Rate: Percentage of failed requests
  - Throughput: Requests per second
  - Saturation: Resource utilization

### SLO (Service Level Objective)
- **Definition**: Target value for SLI
- **Best Practices**:
  - Set realistic SLOs based on business requirements
  - Use SLOs to drive reliability improvements
  - Monitor SLOs continuously
  - Alert on SLO breaches
  - Use error budgets for balancing reliability and innovation

### Error Budget
- **Definition**: Allowable amount of unreliability
- **Calculation**: Error Budget = 100% - SLO
- **Best Practices**:
  - Use error budget to guide release decisions
  - Freeze deployments when error budget is exhausted
  - Implement error budget alerts
  - Track error budget consumption
  - Use error budget for reliability planning

### SLO/SLI Examples
```yaml
# SLO configuration
slo_name: "API Availability"
sli_name: "api_availability"
slo_target: 0.999
slo_window: 30d
alert_threshold: 0.998

# SLI calculation
api_availability = 1 - (error_count / total_count)

# Error budget
error_budget = 1 - slo_target
error_budget_remaining = slo_target - current_availability
```

### Monitoring SLOs
- **Tools**:
  - Prometheus and Grafana
  - CloudWatch SLOs
  - Azure Monitor SLOs
  - Stackdriver SLOs
  - SRE-specific tools (Sloth, sli-exporter)

- **Best Practices**:
  - Visualize SLOs in dashboards
  - Alert on SLO breaches
  - Track SLO trends over time
  - Compare SLOs across services
  - Use SLOs for capacity planning

## Observability Best Practices

### The Three Pillars of Observability
- **Metrics**: Quantitative data points
- **Logs**: Discrete events
- **Traces**: Request paths through distributed systems

### Distributed Tracing
- **Core Concepts**
  - Trace: End-to-end request path
  - Span: Individual operation
  - Trace ID: Unique identifier for trace
  - Span ID: Unique identifier for span

- **Best Practices**
  - Use distributed tracing for microservices
  - Implement trace sampling
  - Use trace context propagation
  - Configure trace retention
  - Analyze traces for performance issues

- **Tools**
  - Jaeger
  - Zipkin
  - AWS X-Ray
  - Azure Application Insights
  - Google Cloud Trace

### Observability Patterns
- **RED Method**: Rate, Errors, Duration
- **USE Method**: Utilization, Saturation, Errors
- **Golden Signals**: Latency, Traffic, Errors, Saturation
- **Four Golden Signals**: Latency, Traffic, Errors, Saturation, SLOs

### Observability Maturity Model
- **Level 1**: Basic metrics and logging
- **Level 2**: Structured logging and metrics
- **Level 3**: Distributed tracing
- **Level 4**: Automated alerting and incident response
- **Level 5**: SLO-driven development and error budgets
