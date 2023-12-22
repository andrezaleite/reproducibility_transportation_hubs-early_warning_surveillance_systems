# Proposal of transportation hubs as cornerstones sentinel points in early-warning surveillance systems
<a name="readme-top"></a>
This repository was created for the purposes of reproducibility and publication of data and codes used in the paper "Proposal of transportation hubs as cornerstones sentinel points in early-warning surveillance systems".

The databases and codes used in this work will be detailed below.

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
    <li><a href="#license">License</a></li>
    <li><a href="#authors-and-contact">Authors and Contact</a></li>
    <li><a href="#acknowledgments">Acknowledgments</a></li>
  </ol>
</details>

## About the project

Responding to emerging pathogens is a top priority and requires identification of their origin and timely determination of transmission routes. In this study, we propose a data-driven approach to identify sentinel hubs for early outbreak detection systems based on the transmission routes originating in each Brazilian city leading to them. We have compiled a comprehensive dataset on human intercity mobility in Brazil, spanning air, road and waterway transport. Using the Ford-Fulkerson algorithm, we rank cities according to their suitability as sentinel hubs and determine the likely routes and number of steps it would take to achieve widespread transmission across the country. Validation with epidemiological and genetic data from SARS-CoV-2 supports our findings. Our results provide important clues for effective pathogen surveillance.

## Database Description

The databases used in this work will be detailed below.

### Data for pre-selected cities
| Resource                        | Base                | Description                                                                                                                                                             |
|---------------------------------|---------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Proximity and Betweeness indexs | hub_pop_density.csv | Metrics associated with each municipality are employed to rank cities based on their network importance, as outlined in the manuscript. Variables description at Dic 1. |

### Data to run Ford Fulkerson Algoritm
| Resource         | Base                             | Description                                                                                                                    |
|------------------|----------------------------------|--------------------------------------------------------------------------------------------------------------------------------|
| Adjacency matrix | adjacency_matrix_correct.parquet | Matrix describing intercity connection. Cities are identifyed according to the IBGE code provided in the hub_pop_density data. |

### Raw data for figures
| Resource                                                                                    | Base                        | Description                                                                                                        |
|---------------------------------------------------------------------------------------------|-----------------------------|--------------------------------------------------------------------------------------------------------------------|
| Figure 1: Average passenger volume in the air mobility network from 2017 to 2022            | aero_anac_2007_2023.parquet | Raw data used to plot figure 1 of the manuscript                                                                   |
| Figure 2: Brazilian mobility network for road and water transportation.                     | fluvi_road_ibge.parquet     | Raw data to reproduce Figure 2 of the manuscript.                                                                  |
| Figure 3: Mobility patterns from Manaus/AM, Recife/PE, Rio de Janeiro/RJ, and São Paulo/SP. | union_paths.csv             | Raw data to reproduce Figure 3 of the manuscript.                                                                  |
| Figure 4: Transmission path patterns of cities in Acre State                                | union_paths.csv             | Raw data to reproduce Figure 4 of the manuscript.                                                                  |
| Figure 5: Epidemiological validation of pathogen transmission pathways.                     | municipios.csv              | "Raw data to reproduce Figure 5 of the manuscript. Use ""validação covid alfa"" script to help getting the plot."  |

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Codes

The scripts used in this work will be detailed below.


| Resource                        | Notebooks                                 | Description                                                                                                                                                                                     |
|---------------------------------|-------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Descriptive analysis ANAC       | Descriptive analisis ANAC.ipynb           | In this script you will find the results of the subsection: "Spatial-temporal analysis of national air transportation". The database required to run this script is aero_anac_2007_2023.parquet |
| Descriptive analysis IBGE       | Descriptive analysis IBGE.ipynb           | In this script you will find the results of the subsection: "Brazilian road and fluvial intercity mobility landscape". The database required to run this script is fluvi_road_ibge.parquet      |
| Proximity and Betweeness indexs | Hub analysis with IBGE indicators.ipynb   | Code to select cities according to the BI index.                                                                                                                                                |
| Ford Fulkerson                  | FF_RJ_Parallel.ipynb                      | Code to run the FF alghorithm and generate the analysis of the manuscript.                                                                                                                      |
| Validation covid (alpha)        | path_validation_covid_cases.ipynb         | Script to access Epidemiological validation of pathogen transmission pathways. The open databases are detailed on the notebook                                                                  |
| Validation covid (gamma)        | path_validation_covid_variate_gamma.ipynb | Script to access dissemination of the Gamma variant from Manaus. The open databases are detailed on the notebook                                                                                |

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

Loading...

<p align="right">(<a href="#readme-top">back to top</a>)</p>

