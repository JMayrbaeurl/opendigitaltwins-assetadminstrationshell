# Open Digital Twins ontology for the Industrie 4.0 Asset Administration Shell

The [Industrie 4.0 Asset Administration Shell (AAS)](https://www.plattform-i40.de/IP/Redaktion/EN/Downloads/Publikation/Asset_Administration_Shell_Reading_Guide.html) is an open standard for the exchange of information between partners in the manufacturing value chain. The Asset Administration Shell (AAS) is the digital representation of an asset. We also call it a “digital twin”. The AAS consists of a number of submodels in which all the information and functionalities of a given asset – including its features, characteristics, properties, statuses, parameters, measurement data and capabilities – can be described.

Microsoft has defined an open standard for describing models of device and logical digital twins, the [Digital Twin Definition Language (DTDL)](https://github.com/Azure/opendigitaltwins-dtdl/blob/master/DTDL/v2/dtdlv2.md). This effort has been brought into the Digital Twin Consortium’s [Open Source Collaboration Acceleration](https://www.digitaltwinconsortium.org/hot-topics/open-source.htm) initiative. Ontologies for [Smart Cities](https://techcommunity.microsoft.com/t5/internet-of-things/smart-cities-ontology-for-digital-twins/ba-p/2166585), [Smart Buildings](https://techcommunity.microsoft.com/t5/internet-of-things/realestatecore-a-smart-building-ontology-for-digital-twins-is/ba-p/1914794) and [Energy Grids](https://techcommunity.microsoft.com/t5/internet-of-things/energy-grid-ontology-for-digital-twins-is-now-available/ba-p/2325134) have been published.  

The authors of this GitHub repository have trialed the applicability of using the AAS as a base for building an ontology for Smart Production (Discrete Manufacturing, Process Manufacturing and Automotive Production). 

# Implementation with DTDL v2

The Asset Administration Shell is defined as a meta model. Implementing all essential models in DTDL was straightforward given the capabilities of DTDL.  

![High level architecture!](Assets\images\Figure_1_Implemented_AAS_Metamodel_and_Submodels.png)

Figure 1: Implemented AAS Metamodel and Submodels 

The DTDL JSON files all passed the [DTDL Validator](https://github.com/Azure-Samples/DTDL-Validator). When importing the models into the [Azure Digital Twin Explorer](https://github.com/Azure-Samples/digital-twins-explorer), you get the following model graph: 

![High level architecture!](/Assets/images/Figure_2_Asset_Administration_Shell_meta_model_graph.png)

Figure 2: Asset Administration Shell meta model graph

# Extensibility through Submodels

A powerful key concept of the AAS metamodel is that all relevant information is provided by submodels. Submodels can contain other submodels.  

**Pro:**  

- This enables a high degree of independence from the entire supply chain in building and operating digital twins. 

- The effort to build an DTDL implementation of the meta model is low. 

**Con:**  

- The submodels have for the most part a very fixed structure. In other ontologies, these structure would have been designed in dedicated models. This implicates that there must be diligence in complying with the modeling requirements – to accomplish data integrity. 

The example below illustrates this challenges. For the submodel “Nameplate” ([source](https://www.plattform-i40.de/IP/Redaktion/DE/Downloads/Publikation/Submodel_Templates-Asset_Administration_Shell-digital_nameplate.pdf?__blob=publicationFile&v=2)) the properties within are fully specified. [MLP= MultiLanguageProperty]. 

![High level architecture!](/Assets/images/Figure_3_Sample_properties_of_submodel_Nameplate.png)

Figure 3: Sample properties of submodel "Nameplate"

# Samples

We implemented two samples: 

1. The example from the Industrie 4.0 “From idea to implementation” on page 36/37 where “Nameplate” was still referred to as “Identification”.   

![High level architecture!](/Assets/images/Figure_4_Sample_from_the_Industrie_40_documentation.png)

Figure 4 Sample from the Industrie 4.0 documentation 

![High level architecture!](/Assets/images/Figure_5_Twin_graph_from_the_first_sample.png)

Figure 5 Twin graph from the first sample

2. The Hilscher Iot Edge Gateway from the set of on pages 55-57 in the same document 

![High level architecture!](/Assets/images/Figure_6_Second_sample_from_the_Industrie_40_documentation_with_Hilscher.png)

Figure 6 Second sample from the Industrie 4.0 documentation with Hilscher 

![High level architecture!](/Assets/images/Figure_7_Hilscher_netIOT_Edge_Gateway_submodels.png)

Figure 7 Hilscher netIOT Edge Gateway submodels 

![High level architecture!](/Assets/images/Figure_8_Twin_graph_from_the_second_sample.png)

Figure 8 Twin graph from the second sample

# Example UI to Automate Twin Creation using the AAS Model

![High level architecture!](/Assets/images/Figure_9.png)

Figure 9 Digital Twin Sample Client App 


![High level architecture!](/Assets/images/Figure_10.png)

Figure 10 New instance in ADT Explorer 

Since customers may have their own sub model properties, we can also generate dynamic UI based on the model properties to automate the instance creation in Azure Digital Twin. 

# Industrie 4.0 Resources 

- „Details of the Asset Administration Shell, Part 1 & 2,“ 11/2020: https://bit.ly/3phSUYB  

- “A short introduction to properties, submodels & Asset Administration Shells (AAS)”:  https://www.plattform-i40.de/IP/Redaktion/EN/Downloads/Publikation/Hardshell-softcore_ppt.html  

- „What is Industrie 4.0?“: https://bit.ly/3kaRz2N  

- „The Asset Administration Shell: Implementing digital twins for use in Industrie 4.0, A starter kit for developers,“ 12/2019: https://bit.ly/3kZZSPl   

- „Details of the Administration Shell - from idea to implementation,“ 07/2019: https://bit.ly/2H8c2Hn  

- „Structure of the Administration Shell,“ 04/2018: https://bit.ly/34jbHdo 

- „What is the Asset Administration Shell from a technical perspective?“ 04/2021: https://bit.ly/3d0kvbw  

- „Examples of the Asset Administration Shell for Industrie 4.0 Components,“ 04/2017: https://bit.ly/2Ti9tVC  
