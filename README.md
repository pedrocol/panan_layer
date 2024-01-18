# panan_layer
Using the base PanAn config (https://github.com/COSIMA/mom6-panan/tree/panan-01) we developed a layer version of this config, with the final end of combining it with ice-shelves


Matt Harrison proposed a realistic PanAn 0.5deg configuration

https://github.com/MJHarrison-GFDL/MOM6-IceShelf-examples/tree/master/ice_ocean_SIS2/Ant0_5deg

However, this configuration has a very simplistic approach for the vertial coordinate, simply

LIGHTEST_DENSITY = 1027.1524    !   [kg m-3] default = 1027.0
                                ! The reference potential density used for the surface interface.
DENSITY_RANGE = 2.0             !   [kg m-3] default = 2.0
                                ! The range of reference potential densities across all interfaces.

There are other realistic configurations in MOM6-exemples that use layer coords. The approach is the following
