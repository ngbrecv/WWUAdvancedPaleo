1.) Download a dataset from the Paleobiology Database that includes all Ordovician-age animals (i.e., Animalia). Name the object Ordovician. What code did you use?

> Ordovician <- velociraptr::downloadPBDB(Taxa = "Animalia", StartInterval="Ordovician",StopInterval = "Ordovician")


2.) Clean up the poorly resolved genus names. What function and/or code did you use?

> Ordovician <- velociraptr::cleanTaxonomy(Ordovician,"genus")

3.) Turn you object Ordovician into a community matrix of the samples by genera, where the samples are different geoplate codes. Geoplate codes denote different paleocontinents, so by doing this, your community matrix will list which genera were present on which paleocontinents during the Ordovician. Cull this matrix so that each sample has a minimum of 25 taxa and each taxon occurs in at least two samples. Show your code.

> OrdoGeoplates <- velociraptr::presenceMatrix(Ordovician,Rows="geoplate",Columns="genus")
> OrdoGeoplates <- velociraptr::cullMatrix(OrdoGeoplates,Rarity=2,Richness=25)

4.) Preform a DCA on your new community matrix. Analyze your DCA with a plot. Do you think that the orientation of samples along either axis 1 or axis 2 is related to the average latitude or longitude of each plate in question? Explain how you determined your answer, and shwo your code. Hint: information about the paleolatitude and paleolongitude of different geoplates is included in the data you originally downloaded (i.e., the object Ordovician)

> OrdoGeoplatesDCA<-vegan::decorana(OrdoGeoplates,ira = 0)

By viewing the Ordovician object,

> View(Ordovician)

and the DCA data,

> OrdoGeoplatesDCA

Axis lengths    4.0836 5.8066 2.8025 3.8765

> plot(OrdoGeoplatesDCA,display = "sites")

I looked at the axis lengths of the first and second DCA, 4.0836 and 5.8066 respectively, and the range of the longitude and latitude, ~(-167) to 172 and ~(-72) to 83 respectively. Since DCA2 has the greatest spread (axis length) and the longitude has the greatest range, DCA2 is likely related to the longitude. DCA1 had a smaller spread than DCA2, a smaller axis length, so it is probably related to the latitude since the latitude had a smaller range.
