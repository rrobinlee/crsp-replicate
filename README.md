### WRDS Data Loader

```{python}
from wrdsloader import WRDSloader

dl = WRDSloader()
dl.download("crsp", "msf")
dl.download("crsp", "msf", date_col="date", start_year=2010, end_year=2023)
dl.download(library="compustat",
            table="funda",
            date_col="datadate",
            start_year=2000,
            end_year=2023,
            signal_cols="gvkey, datadate, at, sale, ni",
            extra_query="AND indfmt='INDL' AND datafmt='STD' AND popsrc='D' AND consol='C'",)
dl.download("taq", "ct_20230103", chunksize=500_000)
```
