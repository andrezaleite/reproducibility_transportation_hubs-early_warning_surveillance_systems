# Human mobility patterns to inform sampling sites for early pathogen detection and routes of spread: a network modeling and validation study
<a name="readme-top"></a>
This repository was created for the purposes of reproducibility and publication of data and codes used in the paper "Human mobility patterns to inform sampling sites for early pathogen detection and routes of spread: a network modeling and validation study".

The databases and codes used in this work will be detailed below.
To access the data used in the work go to https://doi.org/10.5061/dryad.bzkh189j5.

<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
    </li>
  <li>
      <a href="#database-description">Database Description</a>
      <ul>
        <li><a href="#data-for-pre-selected-cities">Data for pre-selected cities</a></li>
      </ul>
    <ul>
        <li><a href="#data-to-run-ford-fulkerson-algoritm">Data to run Ford Fulkerson Algoritm</a></li>
      </ul>
       <ul>
        <li><a href="#raw-data-for-figures">Raw data for figures</a></li>
      </ul>
    </li>
    <li>
      <a href="#codes">Codes</a>
    </li>
    <li>
      <a href="#dashboard">Dashboard</a>
    </li>
    <li><a href="#license">License</a></li>
    <li><a href="#authors-and-contact">Authors and Contact</a></li>
    <li><a href="#acknowledgments">Acknowledgments</a></li>
  </ol>
</details>

## About the project

**Background**: Detecting and foreseeing pathogen dispersion is crucial in preventing widespread disease transmission. Human mobility is a critical issue in human transmission of infectious agents. Through a mobility data-driven approach, we determined municipalities in Brazil that could make up an advanced sentinel network, allowing for early detection of circulating pathogens and their associated transmission routes. 

**Methods**: We compiled a comprehensive dataset on intercity mobility spanning air, road, and waterway transport and constructed a graph-based representation of Brazil’s mobility network. The Ford-Fulkerson algorithm was employed to rank cities according to their suitability as sentinel hubs.

**Findings**: Our results disentangle the complex transportation network of Brazil, with flights alone transporting 79·9 million (CI 58·3 to 101·41 million) passengers annually during 2017-22, seasonal peaks occurring in late spring and summer, and roadways with a maximum capacity of 78·3 million passengers weekly. We ranked the 5,570 Brazilian cities to offer flexibility in prioritizing locations for early pathogen detection through clinical sample collection. In particular, considering mobility patterns to strategically relocate the sentinel units in Brazil's existing flu syndrome surveillance network, we achieved a 17.6% improvement in mobility coverage without the need to increase the number of sentinel sites. Our findings are validated by genetic data collected during the SARS-CoV-2 pandemic period. The proposed mobility-based spread model could recapitulate the dissemination patterns observed during the pandemic. By providing essential clues for effective pathogen surveillance, our results have the potential to inform public health policy and improve future pandemic response efforts.

**Interpretation**: Our results unlock the potential of designing country-wide clinical sample collection networks using mobility data-informed approaches, an innovative practice that can improve current surveillance systems.

**Funding**: Rockefeller Foundation grant 2023-PPI-007 awarded to MB-N.


## Database Description

The databases used in this work will be detailed below.

### Data for pre-selected cities
| Resource                        | Base                | Description                                                                                                                                                             |
|---------------------------------|---------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Proximity, Betweenness indexes, density and pagerank | cities_metrics_all.csv | Metrics associated with each municipality are employed to rank cities based on their network importance, as outlined in the manuscript.|

### Data to run Ford Fulkerson Algoritm
| Resource         | Base                             | Description                                                                                                                    |
|------------------|----------------------------------|--------------------------------------------------------------------------------------------------------------------------------|
| Adjacency matrix | adjacency_matrix_correct.parquet | Matrix describing intercity connection. Cities are identified according to the IBGE code provided in the hub_pop_density data. |
| Temporality analysis | adjacency_matrix_month_1.parquet; adjacency_matrix_month_4.parquet; adjacency_matrix_month_6.parquet; adjacency_matrix_month_7.parquet; adjacency_matrix_month_12.parquet | Matrix describing intercity connection for each month observed in temporality analysis for São Paulo, Rio de Janeiro, Recife e Manaus |


### Raw data for figures
| Resource                                                                                    | Base                        | Description                                                                                                        |
|---------------------------------------------------------------------------------------------|-----------------------------|--------------------------------------------------------------------------------------------------------------------|
| Figure 1: Average passenger volume in the air mobility network from 2017 to 2022            | aero_anac_2017_2023.parquet | Raw data used to plot figure 1 of the manuscript                                                                   |
| Figure 2: Mobility patterns from Manaus/AM, Recife/PE, Rio de Janeiro/RJ, and São Paulo/SP. | adjacency_matrix_correct.parquet     | Raw data to reproduce Figure 2 of the manuscript.                                                                  |
| Figure 3: Transmission routes for cities in the state of Acre, North Brazil. | adjacency_matrix_correct.parquet             | Raw data to reproduce Figure 3 of the manuscript.                                                                  |
| Figure 4: Comparing the mobility-informed configuration for clinical sample collection to the current sentinel network | ms_and_mob_70.csv            | Raw data to reproduce Figure 4 of the manuscript.                                                                  |
| Figure 5: Epidemiological validation of pathogen transmission pathways                     | municipios.csv; Phylo_clade_i_rj_grouped_with_mobility.csv; Phylo_clade_i_sp_grouped_with_mobility.csv; Phylo_clade_ii_sp_grouped_with_mobility.csv;  Phylo_clade_ii_rj_grouped_with_mobility.csv             | Raw data to reproduce Figure 5 of the manuscript.|

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Codes

The scripts used in this work will be detailed below.


| Resource                        | Notebooks                                 | Description                                                                                                                                                                                     |
|---------------------------------|-------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Descriptive analysis ANAC       | Descriptive analisis ANAC.ipynb           | In this script you will find the results of the subsection: "Spatial-temporal analysis of national air transportation". The database required to run this script is aero_anac_2007_2023.parquet |
| Descriptive analysis IBGE       | Descriptive analysis IBGE.ipynb           | In this script you will find the results of the subsection: "Brazilian road and fluvial intercity mobility landscape". The database required to run this script is fluvi_road_ibge.parquet      |
| Proximity and Betweeness indexs | Hub analysis with IBGE indicators.ipynb   | Code to select cities according to the BI index.                                                                                                                                                |
| Ford Fulkerson                  | FF_RJ_Parallel.ipynb                      | Code to run the FF alghorithm and generate the analysis of the manuscript.                                                                                                                      |

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Dashboard

A dashboard enabling direct access to state hubs ranking, gateway cities and paths of transmissions is  (<a href="https://aesop.outerlamce.com/sankey">available</a>) and described in the repository, under the visualization folder.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## License

Distributed under the CC0-1.0 license. See `LICENSE.txt` for more information.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Authors and Contact

**Authors:** Andrêza L. Alencar, Maria Célia L. S. Cunha2, Juliane F. Oliveira, Adriano O. Vasconcelos, Gerson G. Cunha, Ray B. Miranda, Fábio M. H. S. Filho, Corbiniano Silva2, Antônio R. K. Cunha, Thiago Cerqueira-Silva, Luiz Landau, Manoel Barral-Netto, Pablo I. P. Ramos

**Contact:** andreza.leite@ufrpe.br, juliane.oliveira@fiocruz.br 

Paper Link: [Preprint](link)

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Acknowledgments

This study is part of the Alert-Early System of Outbreaks with Pandemic Potential (<a href="http://aesop.health">ÆSOP</a>), an initiative under development by Brazil’s Fundação Oswaldo Cruz (Fiocruz) and the Federal University of Rio de Janeiro with financial support from the Rockefeller Foundation’s Health Initiative (Grant 2023-PPI-007 awarded to M-BN). The excellent project management and administrative support from Fundação de Apoio à Fiocruz (FIOTEC) is greatly appreciated.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

