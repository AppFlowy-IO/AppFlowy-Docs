# Grid (WIP)
This document will explain how the grid works on the Dart side. Also, it can be a development guide 
when you want to be a grid contributor. This document will get updated continuously, and any suggestions
would be helpful.


## Cache
![file : grid_data_cache.plantuml](https://raw.githubusercontent.com/AppFlowy-IO/docs/main/uml/output/block_row_cell_relation.svg)

When you open a grid, the `GridBloc` will be initialized. Look at the diagram shown below, there are four cache classes.

1. GridFieldCache

    * Listen on the field's change
    * Update the field according to the `GridFieldChangeset`. 

2. GridBlockCache

    A Grid contains lots of blocks, each block has a `GridRowCache`. For the moment, we only implement one block.
    * Listens on the block's changeset
    * Update the `GridRowCache` according to the `GridBlockChangeset`. The changeset contains insert/delete/update rows.
  

3. GridRowCache

    * Cache the block's rows in memory
    * A row contains lots of cells, each cell will be cached in the `GridCellCache`.
    * Insert / delete / update row
   
4. GridCellCache

    * Cache each cell by `GridCellCacheKey` in memory
    * Remove / Insert cell 


## Field
Field is represent as the column of the grid. The Field editor is used to edit the field.

![file : grid_field.plantuml](https://raw.githubusercontent.com/AppFlowy-IO/docs/main/uml/output/Field_Editor.svg)


![file : grid_field.plantuml](https://raw.githubusercontent.com/AppFlowy-IO/docs/main/uml/output/Field_Type_Option_Editor.svg)


## Cell
![file : grid_field.plantuml](https://raw.githubusercontent.com/AppFlowy-IO/docs/main/uml/output/Grid_Cell_Builder.svg)


![file : grid_field.plantuml](https://raw.githubusercontent.com/AppFlowy-IO/docs/main/uml/output/Grid_Cell_Controller.svg)


Thank your for reading.