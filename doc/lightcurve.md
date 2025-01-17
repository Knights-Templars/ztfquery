***
_lightcurve.py documentation_
***

`ztfquery.lightcurve.py` is module to access the [IRSA lightcurve service]((https://irsa.ipac.caltech.edu/docs/program_interface/ztf_lightcurve_api.html)

*These are not lightcurves generated from alert packets. These are from the matching the epochal catalogs. Totally independent of alerts. The variable star/AGN community will be most interested in these.*


# Requirements 
- You need an account on [irsa](https://irsa.ipac.caltech.edu/docs/program_interface/ztf_lightcurve_api.html)

*** 


# Getting IRSA LightCurves

*These are not lightcurves generated from alert packets.*

You can directly query the lightcurve by coordinates by doing (Ra, DEC and radius in arcsec):
```
from ztfquery import lightcurve
lcq = lightcurve.LCQuery()
lcq.query_position(197.501495, +75.721959, 5)
```
Data are stored in `lcq.data`.

To plot the lightcurve, simply do:
```
lcq.show()
```

You can also query by ID:
```
from ztfquery import lightcurve
lcq = lightcurve.LCQuery()
lcq.query_id([686103400067717,686103400106565])
```

or any kind of query using the list of parameter from the [LightCurve Query API](https://irsa.ipac.caltech.edu/docs/program_interface/ztf_lightcurve_api.html)

```
from ztfquery import lightcurve
lcq = lightcurve.LCQuery.download_data(circle=[298.0025,29.87147,0.0014], bandname="g")
```
