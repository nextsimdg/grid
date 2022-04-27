# Horizontal grids for `nextsim-DG`

## Bi-hemispheric 1 degree version, based on ORCA1 (NEMO)

### Northern Hemisphere domain

<p align="center">
  <img width="720" src="https://github.com/nextsimdg/grid/blob/main/figs/1degree/NH_35W_f_OUT_ortho.svg">
</p>

*Zoomable vectorial image: [here!](https://raw.githubusercontent.com/nextsimdg/grid/main/figs/1degree/NH_35W_f_OUT_ortho_WHITE.svg)*

<p align="center">
  <img width="720" src="https://github.com/nextsimdg/grid/blob/main/figs/1degree/NH_130E_f_OUT_ortho.svg">
</p>

*Zoomable vectorial image: [here!](https://raw.githubusercontent.com/nextsimdg/grid/main/figs/1degree/NH_130E_f_OUT_ortho_WHITE.svg)*

<!--
![**plot**](https://github.com/nextsimdg/grid/blob/main/figs/1degree/NH_35W_f_OUT_ortho.svg) <br>
Zoomable vectorial image: [here!](https://raw.githubusercontent.com/nextsimdg/grid/main/figs/1degree/NH_35W_f_OUT_ortho.svg)
![**plot**](https://github.com/nextsimdg/grid/blob/main/figs/1degree/NH_130E_f_OUT_ortho.svg) <br>
Zoomable vectorial image: [here!](https://raw.githubusercontent.com/nextsimdg/grid/main/figs/1degree/NH_130E_f_OUT_ortho.svg)
-->

<br>

<p align="center">
  <img width="400" src="https://github.com/nextsimdg/grid/blob/main/figs/1degree/NH_cell_area_+_iso-lat_+_mask.png">
  <br>
  <i>Local resolution of grid cells, iso-latitudes and land-sea mask.</i>
</p>


<br>


### Southern Hemisphere domain

<p align="center">
  <img width="720" src="https://github.com/nextsimdg/grid/blob/main/figs/1degree/SH_35W_f_OUT_ortho.svg">
</p>

*Zoomable vectorial image: [here!](https://raw.githubusercontent.com/nextsimdg/grid/main/figs/1degree/SH_35W_f_OUT_ortho_WHITE.svg)*

<p align="center">
  <img width="720" src="https://github.com/nextsimdg/grid/blob/main/figs/1degree/SH_130E_f_OUT_ortho.svg">
</p>

*Zoomable vectorial image: [here!](https://raw.githubusercontent.com/nextsimdg/grid/main/figs/1degree/SH_130E_f_OUT_ortho_WHITE.svg)*


<!--
![**plot**](https://github.com/nextsimdg/grid/blob/main/figs/1degree/SH_35W_f_OUT_ortho.svg) <br>
Zoomable vectorial image: [here!](https://raw.githubusercontent.com/nextsimdg/grid/main/figs/1degree/SH_35W_f_OUT_ortho.svg)
![**plot**](https://github.com/nextsimdg/grid/blob/main/figs/1degree/SH_130E_f_OUT_ortho.svg) <br>
Zoomable vectorial image: [here!](https://raw.githubusercontent.com/nextsimdg/grid/main/figs/1degree/SH_130E_f_OUT_ortho.svg)
-->

<br>

<p align="center">
  <img height="400" src="https://github.com/nextsimdg/grid/blob/main/figs/1degree/SH_cell_area_+_iso-lat_+_mask.png">
  <br>
  <i>Local resolution of grid cells, iso-latitudes and land-sea mask.</i>
</p>

<br>


### Content of the netCDF file

We should agree on what exactly this file should contain but for now I had to start with something and here it is. Both the Northern and Southern hemisphere domains are included in this file; with corresponding dimensions and variables being identified with the `*_n` and `*_s` suffixes, respectively.

#### Reminder 

NEMO uses the Arakawa C-grid formalism with *squarish* meshes. As such, the point at the very center of a given mesh is the `T-point`, points defining the 4 corners of mesh are `F-points`.


<p align="center">
  <img width="200" src="https://github.com/nextsimdg/grid/blob/main/figs/Grid-cell_p.svg">
</p>



    netcdf grid_nextsimDG_2xHEMI1 {
    dimensions:
        x_n = 182 ;
        y_n = 290 ;
        x_s = 362 ;
        y_s = 147 ;
    variables:
        byte tmask_n(y_n, x_n) ;
    	    tmask_n:long_name = "Land-Sea mask at T-points (center of mesh)" ;
        byte tmask_s(y_s, x_s) ;
    	    tmask_s:long_name = "Land-Sea mask at T-points (center of mesh)" ;
    	double flon_n(y_n, x_n) ;
    		flon_n:units = "degrees East" ;
    		flon_n:long_name = "Longitude at F-points (corners of mesh)" ;
    	double flon_s(y_s, x_s) ;
    		flon_s:units = "degrees East" ;
    		flon_s:long_name = "Longitude at F-points (corners of mesh)" ;
    	double flat_n(y_n, x_n) ;
    		flat_n:units = "degrees North" ;
    		flat_n:long_name = "Latitude at F-points (corners of mesh)" ;
    	double flat_s(y_s, x_s) ;
    		flat_s:units = "degrees North" ;
    		flat_s:long_name = "Latitude at F-points (corners of mesh)" ;
    	double tlon_n(y_n, x_n) ;
    		tlon_n:units = "degrees East" ;
    		tlon_n:long_name = "Longitude at T-points (center of mesh)" ;
    	double tlon_s(y_s, x_s) ;
    		tlon_s:units = "degrees East" ;
    		tlon_s:long_name = "Longitude at T-points (center of mesh)" ;
    	double tlat_n(y_n, x_n) ;
    		tlat_n:units = "degrees North" ;
    		tlat_n:long_name = "Latitude at T-points (center of mesh)" ;
    	double tlat_s(y_s, x_s) ;
    		tlat_s:units = "degrees North" ;
    		tlat_s:long_name = "Latitude at T-points (center of mesh)" ;
    	double e1t_n(y_n, x_n) ;
    		e1t_n:units = "m" ;
    		e1t_n:long_name = "`dx` of mesh, centered at T-point" ;
    	double e2t_n(y_n, x_n) ;
    		e2t_n:units = "m" ;
    		e2t_n:long_name = "`dy` of mesh, centered at T-point" ;
    	double e1t_s(y_s, x_s) ;
    		e1t_s:units = "m" ;
    		e1t_s:long_name = "`dx` of mesh, centered at T-point" ;
    	double e2t_s(y_s, x_s) ;
    		e2t_s:units = "m" ;
    		e2t_s:long_name = "`dy` of mesh, centered at T-point" ;
    
    // global attributes:
    		:About = "Built using ORCA1 (NEMO) `domain_cfg` file: `domain_cfg_L31_4.0.6_ORCA1_no_t_lev1.nc`" ;
    		:Author = "Generated with `orcaX_to_hemiX.py`, L. Brodeau, 2022" ;
    }


​	r	
