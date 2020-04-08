# covid19cellatlas_semantic_map
A mapping of cell annotations in datasets on https://www.covid19cellatlas.org/ to CL using [matrix_semantic_map](https://pypi.org/project/matrix-semantic-map/)

Scientific context - [HCA/HubMap meeting plenary](https://www.youtube.com/watch?v=gHqBoU4s63U)

__Status: Under development__

### Preliminary investigation of data

Data is stored in hdf5a format.  This can be opened in [annData](https://icb-anndata.readthedocs-hosted.com/en/stable/anndata.AnnData.html)

#### Preliminary inspection:

```python
import anndata
bronchi = anndata.read_h5ad('/Users/davidos/Downloads/vieira19_Bronchi_anonymised.processed.h5ad')
bronchi.obs
ct = bronchi.obs.CellType
set(list(ct))
```
=> 

```
{'B cells',
 'Basal 1',
 'Basal 2',
 'Ciliated 1',
 'Ciliated 2',
 'Club',
 'Dendritic cells',
 'Endothelial',
 'Fibroblasts',
 'Goblet 2',
 'Goblet_1',
 'Ionocytes',
 'Luminal_Macrophages',
 'Lymphatic',
 'Mast cells',
 'Neutrophils',
 'Smooth muscle',
 'T and NK'}
 ```

dot path do use = `obs.CellType` ?
 
### Sketch of work: 

* update matrix_semantic_map to support hdf5a via annData
   * support loading for validation
   * Support storage of map string in file (if poss), otherwise will have to be in seperate mapping JSON file.
   
* Prep file list table (scrape?):
    
 * For each dataset: 
   * Download link: https://covid19.cog.sanger.ac.uk/vieira19_Bronchi_anonymised.processed.h5ad
   * Pub (PMID or DOI): 
   * Labels: bronchi 
  
   
* Map cell types to CL - focussing on lungs & airways.

* Demo queries: 
   * By general type
   * By Synonym
   * Data/ontolgy combo query?
 

  



   



