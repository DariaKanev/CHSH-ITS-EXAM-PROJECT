---
title: Methodology
date: 2023-06-21
Description  : "Our working process"
---

**Methodology**

The project that we have worked on aims to explore and present the data extracted from the Knowledge Graphs (MusicBo and Wikidata) in form of data stories on [Melody website](https://projects.dharc.unibo.it/melody/).

*Stage 1*

The first stage of exploration and extraction of data was based on MusicBo Knowledge Graph.
We also used [MusicBo corpus](https://polifonia.disi.unibo.it/corpus/) (part of the Polifonia Corpus) since MusicBO Knowledge Graph is automatically extracted from natural language texts by applying a custom text-to-Knowledge Graph (text2KG) process to the MusicBO corpus documents.

Prior to the exploration we studied the documentation about the MusicBo KG (Knowledge Graph) on [Github](https://github.com/polifonia-project/musicbo-knowledge-graph). This KG provides its users with information about the role of Bologna in the European musical landscape.

MusicBO Knowledge Graph stores information about the role of music in the city of Bologna from a historical and social perspective. It conveys knowledge about music performances in Bologna and encounters between musicians, composers, critics, and historians who passed through Bologna.

We started with launching simple queries given to us as an example on [MusicBo SPARQL endpoint](https://polifonia.disi.unibo.it/musicbo/sparql) to see to what extend MusicBo KG is different from other KGs that we had used during the course (ArCo, DBpedia, Wikidata) and to define the vocabulary that we can use to query this particular KG. 

Since, during the course, we explored the data about music bands, we decided to check if there is information about other types of musical organisations, more specifically orchestras. To do that we used [FRED](https://arco.istc.cnr.it/txt-amr-fred/) because this tool was originally used to create the MusicBo KG. Thanks to that we managed to discover the resource identifier for orchestras. 
Then we launched the query to discover what kind of properties can be found with the resource identifier for orchestras as a subject or as an object. One of the first results we retrieved was the definition of an orchestra which we later used to create a text field in our [data story](https://melody-data.github.io/stories/published_stories/story_1687782595.724613.html) based on [MusicBo SPARQL endpoint](https://polifonia.disi.unibo.it/musicbo/sparql). 

![Definition](https://github.com/DariaKanev/CHSH-ITS-EXAM-PROJECT/blob/main/content/post/2023/jun/images/img-1.jpg?raw=true)

Here we additionally used the already existing data story about the [MusicBo KG on Melody](https://projects.dharc.unibo.it/melody/musicbo/music_in_bologna_textual_corpus_overview) to see how different elements are encoded when MusicBo SPARQL endpoint is used. 
Then we decided to count how many orchestras are mentioned in the MusicBo KG and presented it as a counter in our data story. 

While exploring the list of properties used with the resource for orchestra we also discovered that there are orchestras mentioned in the connection with various cities so we organised the information about how many orchestras are connected with each of the cities. 

![Query for orchetras in connection with cities](https://github.com/DariaKanev/CHSH-ITS-EXAM-PROJECT/blob/main/content/post/2023/jun/images/img-2.jpg?raw=true)

*Challenges* 

One of the first challenges was connected with the fact that to display a graphic element on Melody, some variables must be named in a particular way, which are ?count for counts and ?label for graphs. Queries with different names for these variables return results on MusicBo endpoint, but do not visualize on Melody. 

While searching for orchestras connected with cities, we discovered that San Petronio, which is the name of the main basilica in Bologna is marked as a city. That means that the counter for orchestras mentioned with Bologna should have showed a different number. Such a result must have been shown due to automatic extraction of the MusicBo KG.
Another challenge that we faced related to the fact that querying the KG returned only three results of orchestras names. What’s more two of them definitely referred to the same orchestra name but with different spelling. 

![Query for orchetras mentioned with names](https://github.com/DariaKanev/CHSH-ITS-EXAM-PROJECT/blob/main/content/post/2023/jun/images/img-3.jpg?raw=true)

We hypothesized that there must be more in the original corpus. In this regard we addressed the MusicBo corpus. During the investigation we encountered several problems with the search related to orchestras.

Firstly, we typed "orchestra" in the query field, and we selected the type "lemma," the module "Musicbo," and the language “English” in the available search options. But we failed in our first attempt, we were shown the message "The lemma orchestra is associated with 0 sentences." To solve this problem, we made several additional attempts, including changing the type from “lemma” to “keyword” and “entity”. However, all these efforts resulted in either 0 or 1.

In our next attempt, we unintentionally selected the term "orchestra" from a drop-down box that appeared for selection, we clicked “RUN”, and received a different result. The message displayed was "The lemma orchestra is associated with 1383 sentences." Considering all of this, we stated that the selection from the drop-down box was necessary for obtaining results. However, when we checked again the following day this bug had been fixed.

Secondly, another problem we encountered was the inconsistency between the selected language (English) and the language of the obtained sentences. Despite setting the language to English, the first three sentences were in Italian. However, our research focused on investigating sentences exclusively in English.

![Search in Polifonia Corpus](https://github.com/DariaKanev/CHSH-ITS-EXAM-PROJECT/blob/main/content/post/2023/jun/images/img-4.jpg?raw=true)

Finally, when attempting to view all 1383 sentences, we encountered another problem. Although we clicked on the "More+" option to display more sentences, only 430 of them were displayed. We attempted to increase the number of displayed sentences by adjusting the "N line", even setting it to 1000+, but this did not resolve the issue. To address this problem, we attempted to incrementally modify the query by clicking “+” and adding digits one by one, but this approach did not solve the problem.

In summary, as a result of the investigation, out of 427 English sentences, the word orchestra is used with a name in 26 sentences, and this corresponds to approximately 6%. This discovery proved our hypothesis that there are more orchestras mentioned with names and showed another weak point of automatic creation of a KG.

Examples of the sentences are below: 
1.	Sentence n. 6 I gathered much more congenial instruction about it from Hoffmann's Phantasiestucken than from my Leipzig orchestra player; and now came the time when I really lived and breathed in Hoffmann's artistic atmosphere of ghosts and spirits.
2.	Sentence n. 9 My mother, indeed, paid the violinist Sipp (who was still playing in the Leipzig orchestra in 1865) eight thalers for a violin (I do not know what became of it), with which for quite three months I must have inflicted unutterable torture upon my mother and sister by practising in my tiny little room.
3.	Sentence n. 20 The only circumstance against me was the fact that Louis Schubert, the famous musician whom I had known from very early times as the first violoncellist of the Magdeburg orchestra, had come to Konigsberg from Riga, where the theatre had been closed for a time, and where he had left his wife, in order to fill the post of musical conductor here until the new theatre in Riga was opened, and he could return.
4.	Sentence n. 44 the Berlin orchestra he had acquired the habit of marking the note that he wished to be brought out with the word diese (this), which at first was quite incomprehensible to me.
5.	Sentence n. 79 Legrenzi's orchestra at San Marco in Venice, 1685, consisted of 34 players distributed as follows:27 Cornetti 2 Violini 8 Violette 11 Viole da braccio 2 [tenor violas?]
6.	Sentence n. 86 Cazzati molded the San Petronio orchestra into one of the finest instrumental ensembles in Europe, and when he left Bologna in 1671 after a heated argument with the organist Giulio Arresti,^^ NUMBER 3 5 31 TARLE 1.—Numbers of regularly employed musicians at San Petronio from 1657 until 1671 (data from Bologna, "Liste e Ricevute" and "Mandati mensili") Instrument Treble instruments Violin Alto Viola Basso continuo instr
7.	Sentence n. 103 Legrenzi's orchestra at San Marco in Venice, for example, included thirty-four instruments in 1685, approximately a third of which played the continuo (Table 7) .
8.	Sentence n. 104 Similarly in Rome, Arcangelo Corelli's orchestra at San Lorenzo in Damaso included a comparable continuo force in 1692 (Table 8 ) .
9.	Sentence n. 105 NUMBER 35 39 TABLE 7.—Number of instruments in Legrenzi's orchestra at San Marco in 1685 (data from Caffi, Storia delta Musica, vol.
10.	Sentence n. 106 3 4 1 3 TABLE 8.—Number of instruments in Corelli's orchestra at San Lorenzo in Damaso in 1692 (data from Schnoebelen, "Performance Practices," page 45) Instrument Violetta.
11.	Sentence n. 127 In 1703 he was engaged as violinist in the orchestra of Prince JohannErnst of Saxe-Weimar, a post which he exchanged the same year for that of organist at Arnstadt.
12.	Sentence n. 137 of thirteen the young Carl had already composed a "grand romantic comic opera"' Das stumme Waldmddchen, and at seventeen he was conducting the Breslau theatre orchestra; but this did not prevent him from trying his hand at criticism and novel-writing, or from working at lithography with its inventor Senefelder and writing a quantity of vocal and piano music, while at the same time leading a disordered life, much to the detriment of his already fragile health.
13.	Sentence n. 147 Strauss can be jocular and severe by turns; his harmony can be bold and dazzling at one moment, only to be succeeded at the next by the facile seduction of the Viennese waltz; and he will exchange the vast orchestra of Salome (105 players) for the modest 36 instrumentalists in Ariadne auf Naxos, Edgar Degas : Musicians in the orchestra.
14.	Sentence n. 164 As a pupil of Mendelssohn and his deputy with the Leipzig orchestra he had, however, merely been an elegant reflection of his master, and his abundant output has practically disappeared from the repertorv.
15.	Sentence n. 193 ”7 The reference to the Napoleonic wars as an explanation for Rossini’s noisy orchestra was elaborated in a curious text published in the Gazzetta di Firenze in 1826, which was purportedly derived from a written report left by Lord Byron of a conversation he had supposedly had with Rossini.
16.	Sentence n. 202 den, I had maintained with Theodor Uhlig, the young musician of the Dresden orchestra, which I have already described, and which by this time had developed into a genuinely productive association.
17.	Sentence n. 284 Gluck invaded the orchestra of the French Opera with trombones, cymbals, and the big drum in the year 1774, when he at the same time ejected the harpsichord, the piano of the period.
18.	Sentence n. 327 A Corelli orchestra therefore requires at least ten players unless the same keyboard instrument accompanies both concertino and tutti.
19.	Sentence n. 342 On his return in 1718 he secured an appointment as oboist with the King of Poland's orchestra, which was more often in Dresden than in Warsaw, a&ct he took lessons on the flute from.
20.	Sentence n. 353 When Frederick himself died in 1786 Kapellmeister Reichart, who had shown himself a vital trainer even under the tyranny, brought the Berlin orchestra to a standard that made Dittersdorf praise it with unusual warmth in his autobiography.
21.	Sentence n. 355 Schubart speaks of the Stuttgart orchestra as 'one of the best in the world* during the Jommelli regime, and as Schubart died in Stuttgart where he was a theatre manager and had previously lived at Mannheim he should Lave been a good Judge.
22.	Sentence n. 365 and which took eight months', for he spoke of the Eisenach orchestra which he directed from 1708 as surpassing 'the famous Parisian opera orchestra which I heard fairly recently'.
23.	Sentence n. 374 CHAPTER XV The Last Phase Aer hearing the Mannheim orchestra Burney wrote: It has long seemed to me as if the variety, taste, spirit, and new effects produced by contrast, and the use of crescendo and diminuendo in these symphonies, had been of more service
24.	Sentence n. 405 They left matters to take care of themselves and, now, we are confronted by the "celebrated" Berlin orchestra in which the last trace of the traditions of Spontini's strict discipline have faded away.
25.	Sentence n. 408 The masterly execution of this passage by the Paris orchestra consisted in the fact that they played it EXACTLY as it is written.
26.	Sentence n. 424 When Marschner, in 1848, found me striving to awaken the spirit of the members of the Dresden orchestra, he seriously dissuaded me, saying he thought professional musicians incapable of understanding what I meant.

Last but not least, while querying the KG, we attempted to establish a connection between orchestras and people mentioned. The queries returned no results for triples containing both these entities. However, when we used an additional variable, we retrieved results, although all of them referred to San Petronio as a person or as a name for the orchestra. We decided to explore this connection using a more extensive KG, namely Wikidata.  

*Stage 2*

The second stage of exploration and extraction of data was based on Wikidata Knowledge Graph. We decided it would be relevant to complete the data about orchestras extracted from another KG. We searched on [Wikidata service](https://query.wikidata.org/) for resource identifier for orchestra and then created a query to see how many orchestras there are in Italy. We published this information as a counter in our [second data story](https://melody-data.github.io/stories/published_stories/story_1687783155.447632.html) which used [Wikidata endpoint](https://query.wikidata.org/sparql).

Then we started to explore what kind of data can be found on Wikidata about orchestras from Italy and decided to organise them in a table. However, the information we wanted to include in our table is not presented for every orchestra which is why we used the operator OPTIONAL in our query.

We thought it would be also interesting to compare it with the number of orchestras in the world and in other European countries. The map in our data story displays orchestras in the world while the numbers for orchestras in Europe are organised in a bar chart.

Since we haven’t found a direct connection between orchestras and people in the MusicBo KG, we launched queries to explore it on Wikidata service and Wikidata endpoint. The most obvious connection was with conductors or art directors. We created a text search for orchestras from different countries where we presented the names of the orchestras with their country of origin as well as the orchestras’ leaders.

Some of these prominent musicians were mentioned on Wikidata in connection with several orchestras. For this reason, we added an action to display all the musical organisations where these musicians participate when this information is available.

*Challenges*

When we launched the query for the map, we realized that very few orchestras in Europe are listed with their exact location unlike surprisingly the orchestras in Mexico. For this reason, we decided to create another query for calculating the total number of orchestras in European countries which returned bigger numbers.

Another challenge was faced when we added an action to the data retrieved using the operator OPTIONAL, because the button that initiated the action query appeared even in case when the field for the leader hadn’t been filled with any information. 

*Stage 3*

The third stage of our group project focused on creating a website to present our project. Since we all had already created a GitHub account to create data stories on Melody, we immediately moved to the next step and created a repository, then we added all the participants of our group as collaborators to this repository. Then we created a website using Hugo. We downloaded the website structure on our PC and using "git" connected the folder on our PC with the repository on GitHub. With the help of “git push” function we transferred the information from a PC to a repository. Following the instruction to Hugo users we managed to apply a theme to our website. While creating the content for pages of our website, we added hyperlinks to the resources we used and to our data stories as well as graphic elements we found relevant to be displayed.

*Challenges*

The first challenge that we encountered was due to the fact that GitHub modified the procedure of creating a website. Unfortunately, the tutorial that had been published only described the previous procedure. That is why we contacted the support and they shared with a link to the new instructions. However, these instructions were much more complicated in terms of adding the theme to a website because they required installation of several software applications on our personal PCs. Another challenge had to do with Jekyll software. Our group decided to appeal to Hugo, because we couldn’t install Jekyll on either of our PCs. As Hugo had detailed instructions on how to apply themes to a website, we decided to use Hugo instead.

While modifying our content we faced several challenges as well. Since we did not work with HTML directly but worked with markdown, we could not insert graphic elements from Melody via embedding, but used pictures instead.

