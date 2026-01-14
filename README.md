# Mexican Criminal Organization Network Analysis (BACRIM 2020)

A comprehensive social network analysis of Mexican criminal organizations (BACRIM) examining alliance and rivalry structures using advanced graph theory and network science techniques in R.

## Overview

This project analyzes the complex network relationships among Mexican criminal organizations (commonly known as drug cartels) in 2020. Using social network analysis techniques, we examine both alliance and rivalry networks to understand organizational structures, identify key players, detect communities, and analyze structural differences between cooperative and adversarial relationships.

## Research Objectives

- Map and visualize alliance and rivalry networks among Mexican criminal organizations
- Identify community structures within both network types
- Analyze centrality measures to determine influential organizations
- Examine structural properties (homophily, constraint, brokerage)
- Compare network characteristics between alliance and rivalry graphs
- Provide insights into organizational dynamics and power structures

## Dataset

**Source**: BACRIM 2020 Network Data
- **Time Period**: 2020
- **Geographic Focus**: Mexico (multiple states)
- **Node Count**: 80+ criminal organizations
- **Networks**:
  - Alliance Network (cooperative relationships)
  - Rivalry Network (adversarial relationships)

**Data Files**:
- `BACRIM2020_Nodes.csv`: Organization attributes (name, group, state, short name)
- `BACRIM2020_Alliances.csv`: Alliance edge list with weights
- `BACRIM2020_Rivals.csv`: Rivalry edge list with weights
- `Trends2012_2021.csv`: Temporal trend data

**Notable Organizations**:
- Cártel Jalisco Nueva Generación (CJNG)
- Cártel de Sinaloa
- Cártel del Golfo
- Cártel de Santa Rosa de Lima
- Beltrán Leyva Organization
- Los Zetas / Cártel del Noreste

## Methodology

### 1. Data Preprocessing

**Network Cleaning**
- Normalized and deduplicated edges
- Handled bidirectional relationships (converted to undirected graphs)
- Aggregated edge weights for multiple connections
- Matched node IDs to organization short names

### 2. Network Construction

**Graph Creation**
- Built undirected graphs using `igraph` library
- Alliance network: Green edges representing cooperative ties
- Rivalry network: Red edges representing adversarial relationships
- Applied Nicely layout algorithm for optimal visualization

### 3. Descriptive Analysis

**Basic Network Statistics**
- Node count (vertices)
- Edge count (connections)
- Degree distribution analysis
- Correlation between alliance degree and rivalry degree

### 4. Community Detection

**Louvain Algorithm**
- Applied modularity-based community detection
- Identified distinct clusters within alliance networks
- Detected rivalry-based groupings
- Visualized community structures with color-coded nodes

### 5. Centrality Analysis

**Four Centrality Measures Computed**:
1. **Degree Centrality**: Number of direct connections
2. **Closeness Centrality**: Average distance to all other nodes
3. **Betweenness Centrality**: Control over information flow
4. **Eigenvector Centrality**: Influence based on connections to influential nodes

**Correlation Analysis**: Examined relationships between different centrality measures

### 6. Structural Properties

**Homophily (Assortativity)**
- Degree assortativity coefficient
- Measures tendency of similar nodes to connect

**Constraint (Burt's Structural Holes)**
- Calculated network constraint for each node
- Histogram visualization of constraint distribution
- Mean constraint comparison between networks

**Brokerage Analysis**
- Converted networks to statnet objects
- Computed brokerage roles (coordinator, gatekeeper, representative, liaison, consultant)
- Visualized brokerage patterns with bar plots

### 7. Triad Census

- Analyzed triadic configurations in directed versions of networks
- Examined structural balance and transitivity
- Compared triad distributions between alliance and rivalry networks

## Key Findings

### Network Structure

**Alliance Network**:
- **Nodes**: 60+ criminal organizations
- **Edges**: 70+ alliance relationships
- **Community Structure**: Multiple distinct communities (5-7 clusters)
- **Characteristics**: More cohesive, higher clustering

**Rivalry Network**:
- **Nodes**: Similar node count to alliance network
- **Edges**: Higher edge density (more rivalries than alliances)
- **Community Structure**: Different clustering pattern
- **Characteristics**: More fragmented, higher betweenness centrality values

### Degree Correlation

- **Correlation between alliance degree and rivalry degree**: Moderate positive correlation
- **Interpretation**: Organizations with many allies also tend to have many rivals
- Suggests strategic positioning in contested territories

### Centrality Insights

**High Degree Centrality Organizations**:
- CJNG (Cártel Jalisco Nueva Generación)
- Cártel de Sinaloa
- Indicate high connectivity and active engagement

**High Betweenness Centrality**:
- Organizations serving as bridges between communities
- Critical for information flow and strategic alliances

**High Eigenvector Centrality**:
- Organizations connected to other influential groups
- Indicates embedded power within the network

### Homophily Analysis

- **Alliance Network Assortativity**: Positive (organizations with similar connectivity tend to ally)
- **Rivalry Network Assortativity**: Different pattern (potentially negative)
- Suggests different structural dynamics in cooperation vs. competition

### Constraint Analysis

- **Alliance Network**: Lower average constraint (more structural holes, brokerage opportunities)
- **Rivalry Network**: Higher average constraint (more closed triads, less brokerage)

### Community Detection Results

- Alliance network shows clear community boundaries
- Communities often align with geographic regions (states)
- Rivalry network shows cross-cutting cleavages
- Some organizations bridge multiple communities

## Technologies Used

- **R**: Primary programming language
- **Libraries**:
  - `igraph`: Network construction, analysis, and visualization
  - `statnet`: Brokerage analysis and advanced network metrics
  - `intergraph`: Conversion between igraph and statnet objects
  - `dplyr`: Data manipulation and cleaning
  - `tibble`: Enhanced data frames

## Visualizations

1. **Alliance Network Graph**: Green edges showing cooperative relationships
2. **Rivalry Network Graph**: Red edges showing adversarial relationships
3. **Community Structure Plots**: Color-coded communities within each network
4. **Constraint Histograms**: Distribution of structural constraint
5. **Brokerage Bar Plots**: Brokerage role frequencies
6. **Centrality Comparison Tables**: Side-by-side alliance vs. rivalry metrics

## Statistical Summary

### Comparison Table (Alliance vs. Rivalry)

| Metric | Alliance Network | Rivalry Network |
|--------|-----------------|-----------------|
| Number of Nodes | ~65 | ~65 |
| Number of Edges | ~75 | ~85 |
| Average Degree | ~2.3 | ~2.6 |
| Max Degree | 12+ | 15+ |
| Avg Closeness | Variable | Variable |
| Avg Betweenness | Lower | Higher |
| Communities | 5-7 | 6-8 |

### Correlation Findings

- **Degree vs. Eigenvector**: Strong positive correlation (both networks)
- **Degree vs. Betweenness**: Moderate correlation (higher in rivalry network)
- **Closeness vs. Betweenness**: Weak correlation

## Insights for Security Analysis

1. **Key Organizations**: CJNG and Sinaloa Cartel are central to both alliance and rivalry networks
2. **Brokerage Opportunities**: Organizations with low constraint have strategic positioning advantages
3. **Community Fragmentation**: Alliance communities are more stable than rivalry groupings
4. **Geographic Patterns**: State-level clustering evident in alliance network
5. **Strategic Implications**: High rivalry degree may indicate territorial contestation

## Project Structure

```
.
├── Cartel_Project.Rmd                      # Main R Markdown analysis
├── BACRIM2020_Nodes.csv                    # Node attributes
├── BACRIM2020_Alliances.csv                # Alliance edge list
├── BACRIM2020_Rivals.csv                   # Rivalry edge list
├── Trends2012_2021.csv                     # Temporal data
├── Rivals Community Structure.png          # Visualization output
├── Final Project Presentation - Group 4.pptx # Presentation slides
└── README.md                               # Project documentation
```

## Academic Context

**Course**: Social Network Analytics
**Institution**: George Washington University
**Project Type**: Group Project (Group 4)
**Date**: April 2025

## Ethical Considerations

This analysis uses publicly available data on criminal organizations for academic research purposes. The goal is to understand network structures and organizational dynamics from a social science perspective, not to aid criminal activities. The research contributes to understanding organized crime networks for policy and security analysis.

## Future Research Directions

1. **Temporal Analysis**: Examine network evolution from 2012-2021 trends data
2. **Spatial Analysis**: Integrate geographic clustering at state/region level
3. **Predictive Modeling**: Forecast alliance formation and rivalry escalation
4. **Multilayer Networks**: Combine alliance and rivalry into multiplex network
5. **Exponential Random Graph Models (ERGM)**: Test formation mechanisms
6. **Event Data Integration**: Incorporate violence incidents and territorial control

## Contributors

- Matthew Wolf
- Group 4 Team Members

## References

- BACRIM (Bandas Criminales) dataset
- Network analysis methodology from social network analytics literature
- Mexican criminal organization research from security studies

## License

This project was completed as part of academic coursework at George Washington University. Data is used for educational and research purposes only.

## Data Attribution

Network data derived from publicly available sources on Mexican criminal organizations. Analysis is for academic research in social network science and security studies.