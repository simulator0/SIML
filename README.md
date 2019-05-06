# MiniDES

The lightweight Distribution-Energy-Simulator (DES) is a basic framework to model distributed energy resources. It allows for synchronized time
progress on arbitrary resource sets and incorporates queries to ease control and
post-processing. Communities are built bottom up as a collection of resource sets/subsets to enable modular and customizable simulation setups. The entire framework resides within a jupyter notebook, offering a template to start modeling right away.

It currently communicates with [OpenDSS](https://sourceforge.net/projects/electricdss/) via file export/import, if power flow studies are performed.

The structure of the framework can be outlined as follows:
```
+-------------------------------------------------------------------+
|      __  ____      _ ___  ________                                |
|     /  |/  (_)__  (_) _ \/ __/ __/                                |
|    / /|_/ / / _ \/ / // / _/_\ \                                  |
|   /_/  /_/_/_//_/_/____/___/___/                                  |
+-------------------------------------------------------------------+
|	generate test data                                                |
|  		sample_recs	        generate rectangular pattern/profile       |
|  		sample_sinus	       generate waveform pattern/profile          |
|	query                                                             |
|  		get_rss	            access helper to return resource objects   |
|  		get_power	          access helper to aggregate resource power  |
|  		get_power_grp	      aggregates the power of a peer/collection  |
|	parameter                                                         |
|  		get_param	          calculatesht chosen parameter              |
|  		get_params          calculatetime+series parameter             |
|	time rollbacks                                                    |
|	  	jump_back	          rollback time/logs to previous state       |
|	general                                                           |
|	  	simulation_init	    generates data model / init. resources     |
|	  	simulation_run	     start the simulation                       |
|	store and load                                                    |
|  		simulation_store    store the simulation results (mdata)       |
|  		simulation_load	    load the simulation results into the model |
|	plot                                                              |
|  		plot_cords	plots    resources by their coordinates             |
|  		plot_logs	plots     one log per given resource                 |
|  		plot_bar	plots      multiple data series (pyplot wrap)         |
|	conversion helpers                                                |
|  		to_kWh              con^ert Ws to kWh                          |
|  		to_Ws               convert kWh to Ws                          |
|  		arc_to_deg          convert radians to great circle distance   |
|  		deg_to_arc          convert the reverse                        |
|  		latlon_to_xyz       convert angluar to cartesian               |
|  		xyz_to_latlon	      convert reverse                            |
|  		gen_coords          generate random coordinate batch           |
|  		center_point        calculate median center of point cloud     |
+-------------------------------------------------------------------+

```

# Install

There are no installation requirements beside a functional [jupyter notebook](https://jupyter-notebook.readthedocs.io/en/stable/
) (JPN) based on python3. Start the juptyer notebook and review the template.

# Wiki

While the functions in the template are annotated, the Wiki describes the workflow and explains the existing models/resources.
