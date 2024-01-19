# panan_layer
Using the base PanAn config (https://github.com/COSIMA/mom6-panan/tree/panan-01) we developed a layer version of this config, with the final end of combining it with ice-shelves


Matt Harrison proposed a realistic PanAn 0.5deg configuration

https://github.com/MJHarrison-GFDL/MOM6-IceShelf-examples/tree/master/ice_ocean_SIS2/Ant0_5deg

However, this configuration has a very simplistic approach for the vertial coordinate, simply

LIGHTEST_DENSITY = 1027.1524    !   [kg m-3] default = 1027.0
                                ! The reference potential density used for the surface interface.
DENSITY_RANGE = 2.0             !   [kg m-3] default = 2.0
                                ! The range of reference potential densities across all interfaces.

There are other realistic configurations in MOM6-exemples that use layer coords. The approach is the following (only one shown, but this is repeated in the other configs)

### ice_ocean_SIS2/OM4_025/

ALE_COORDINATE_CONFIG = "HYBRID:hycom1_75_800m.nc,sigma2,FNC1:2,4000,4.5,.01"
(FILE:lev.nc,interfaces=zw,FNC1:dz_min,H_total,power,precision)
where sigma2 is
 sigma2 = 1010, 1014.3034, 1017.8088, 1020.843, 1023.5566, 1025.813, 
    1027.0275, 1027.9114, 1028.6422, 1029.2795, 1029.852, 1030.3762, 
    1030.8626, 1031.3183, 1031.7486, 1032.1572, 1032.5471, 1032.9207, 
    1033.2798, 1033.6261, 1033.9608, 1034.2519, 1034.4817, 1034.6774, 
    1034.8508, 1035.0082, 1035.1533, 1035.2886, 1035.4159, 1035.5364, 
    1035.6511, 1035.7608, 1035.8661, 1035.9675, 1036.0645, 1036.1554, 
    1036.2411, 1036.3223, 1036.3998, 1036.4739, 1036.5451, 1036.6137, 
    1036.68, 1036.7441, 1036.8062, 1036.8526, 1036.8874, 1036.9164, 
    1036.9418, 1036.9647, 1036.9857, 1037.0052, 1037.0236, 1037.0409, 
    1037.0574, 1037.0738, 1037.0902, 1037.1066, 1037.123, 1037.1394, 
    1037.1558, 1037.1722, 1037.1887, 1037.206, 1037.2241, 1037.2435, 
    1037.2642, 1037.2866, 1037.3112, 1037.3389, 1037.3713, 1037.4118, 
    1037.475, 1037.6332, 1037.8104, 1038 ;


