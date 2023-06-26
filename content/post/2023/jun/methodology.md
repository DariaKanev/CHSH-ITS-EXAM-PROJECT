---
title: Methodology
#date: 2023-06-25
#image : "/images/img-1.jpg"
Description  : "Our working process"
---

**Methodology**

The project that we have worked on aims to explore and present the data extracted from the Knowledge Graphs (MusicBo and Wikidata) in form of data stories on [Melody website](https://projects.dharc.unibo.it/melody/).

Stage 1

The first stage of exploration and extraction of data was based on MusicBo Knowledge Graph.
We also used [MusicBo corpus](https://polifonia.disi.unibo.it/corpus/) (part of the Polifonia Corpus) since MusicBO Knowledge Graph is automatically extracted from natural language texts by applying a custom text-to-Knowledge Graph (text2KG) process to the MusicBO corpus documents.
Prior to the exploration we studied the documentation about the MusicBo KG (Knowledge Graph) on [Github](https://github.com/polifonia-project/musicbo-knowledge-graph). This KG provides its users with the information about the role of Bologna in the European musical landscape.
MusicBO Knowledge Graph stores information about the role of music in the city of Bologna from a historical and social perspective. It conveys knowledge about music performances in Bologna and encounters between musicians, composers, critics and historians who passed through Bologna.
We started with launching simple queries given to us as an example on [MusicBo SPARQL endpoint](https://polifonia.disi.unibo.it/musicbo/sparql) to see to what extend MusicBo KG is different from other KGs that we had used during the course (ArCo, DBpedia, Wikidata) and to define the vocabulary that we can use to query this particular KG. 
Since, during the course, we explored the data about music bands, we decided to check if there is information about other types of musical organisations, more specifically orchestras. To do that we used [FRED](https://arco.istc.cnr.it/txt-amr-fred/) because this tool was originally used to create the MusicBo KG. Thanks to that we managed to discover the resource identifier for orchestras. 
Then we launched the query to discover what kind of properties can be found with the resource identifier for orchestras as a subject or as an object. One of the first results we retrieved was the definition of an orchestra which we later used to create a text field in our [data story](https://melody-data.github.io/stories/published_stories/story_1687782595.724613.html) based on [MusicBo SPARQL endpoint](https://polifonia.disi.unibo.it/musicbo/sparql).  
