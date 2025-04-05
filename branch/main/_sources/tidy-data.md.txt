# Tidy data and dealing with messy data

```{objectives}
- Knowing about the tidy data format
- Be able to reformat tabular data into the tidy data format
```

```{figure} img/tidy-data/spreadsheet.png
:alt: An example spreadsheet not in tidy data format

Example spreadsheet (this is a phantasy dataset, apologies to biology
students/researchers - this is not my domain).
```

```{discussion} What is the problem with storing data like this?
- Format: Limited interoperability with other programs
- Error prone (see e.g. [this famous example](https://www.washingtonpost.com/news/wonk/wp/2013/04/16/is-the-best-evidence-for-austerity-based-on-an-excel-spreadsheet-error/))
- Difficult to parse ("understand") by scripts: difficult to automate
- Not in *tidy format*: difficult to extend/modify
```

How should we arrange the data?

```{figure} img/tidy-data/svalbard-compact.png
:alt: Example data arranged in a compact representation
:width: 30%

Attempt 1: Not great since we need to somehow divide at the comma. How should we deal with multiple sightings?
```

```{figure} img/tidy-data/svalbard-wide.png
:alt: Example data arranged in a wide format
:width: 60%

Attempt 2: Adding observation sites will force us to add columns.
```

```{figure} img/tidy-data/svalbard-transposed.png
:alt: Example data transposed
:width: 60%

Attempt 3: Adding species will force us to add columns.
```

```{figure} img/tidy-data/svalbard-tidy.png
:alt: Example data arranged in tidy data format
:width: 50%

Tidy data format: Columns are variables, rows are observations/measurements. Easy to add new species and sites.
```

```{keypoints} Tidy data format
- [Hadley Wickham: Tidy Data](https://vita.had.co.nz/papers/tidy-data.html)
- Columns are variables
- Rows are observations/measurements
- "Long form"
- Order does not matter
- **Easy to extend** with more species and more sites
  without modifying the code
- **Structure for storing data** - this does not mean that this is ideal
  for tables in presentations or publications
- It is possible to convert between wide form and long form and back
  (e.g. using `pandas.melt` or `pandas.pivot`), see [this example notebook](https://nbviewer.org/github/coderefinery/data-visualization-python/blob/main/notebooks/tidy-data.ipynb)
```


## Use a standard format

```text
Species,Observation site,Number of sightings
arctic fox,A,3
arctic fox,B,1
walrus,B,1
walrus,C,1
reindeer,B,10
reindeer,C,1
polar bear,A,1
polar bear,C,1
seal,A,2
seal,B,1
seal,C,2
```

- **Use a format that is standard in your community, don't invent your own**
- CSV is often a good choice since most visualization tools can read CSV data

There are many more formats (adapted after [Python for Scientific Computing](https://aaltoscicomp.github.io/python-for-scicomp/work-with-data/)):
```{list-table}
:header-rows: 1

* - Name:
  - Human<br>
    readable:
  - Space<br>
    efficiency:
  - Arbitrary<br>
    data:
  - Tidy<br>
    data:
  - Array<br>
    data:
  - Long term<br>
    storage/sharing:

* - [CSV](https://en.wikipedia.org/wiki/Comma-separated_values)
  - ✅
  - ❌
  - ❌
  - ✅
  - 🟨
  - ✅

* - [Feather](https://arrow.apache.org/docs/python/feather.html)
  - ❌
  - ✅
  - ❌
  - ✅
  - ❌
  - ❌

* - [Parquet](https://parquet.apache.org/)
  - ❌
  - ✅
  - 🟨
  - ✅
  - 🟨
  - ✅

* - [NPY](https://numpy.org/doc/stable/reference/generated/numpy.lib.format.html)
  - ❌
  - 🟨
  - ❌
  - ❌
  - ✅
  - ❌

* - [HDF5](https://en.wikipedia.org/wiki/Hierarchical_Data_Format)
  - ❌
  - ✅
  - ❌
  - ❌
  - ✅
  - ✅

* - [NetCDF](https://www.unidata.ucar.edu/software/netcdf/)
  - ❌
  - ✅
  - ❌
  - ❌
  - ✅
  - ✅

* - [JSON](https://en.wikipedia.org/wiki/JSON)
  - ✅
  - ❌
  - 🟨
  - ❌
  - ❌
  - ✅

* - [GeoJSON](https://geojson.org/)
  - ✅
  - ❌
  - 🟨
  - ❌
  - ❌
  - ✅

* - Excel
  - ❌
  - ❌
  - ❌
  - 🟨
  - ❌
  - 🟨

* - Graph formats
  - 🟨
  - 🟨
  - ❌
  - ❌
  - ❌
  - ✅

* - [SQL](https://en.wikipedia.org/wiki/SQL)
  - ❌
  - 🟨
  - ❌
  - ❌
  - ❌
  - ❌
```

```{note}
- ✅ : Good
- 🟨 : Ok / depends on a case
- ❌ : Bad
```



:::{exercise}
We have been given a dataset so that for a given book we know how many copies we have stored in the main public libraries in Helsinki

| Book Title                        | Pasila Library | Oodi Library | Kallio Library |
|----------------------------------|----------------|--------------|----------------|
| Risto Räppääjä ja kauhea makkara | 2              | 1            | 3              |
| Heinähattu ja Vilttitossu        | 1              | 0            | 2              |
| Tatu ja Patu Helsingissä         | 3              | 2            | 1              |
| Risto Räppääjä saa isän          | 2              | 2            | 0              |
| Herra Hakkarainen maailmalla     | 1              | 3            | 2              |
| Koiramäen talossa                | 0              | 2            | 1              |
| Ella ja kaverit salaisessa palveluksessa | 3       | 1            | 2              |


* Is the data **tidy**?
* What is the tidy version of that data?

::::{solution}
| Book Title                        | Library         | Copies |
|----------------------------------|------------------|--------|
| Risto Räppääjä ja kauhea makkara | Pasila Library   | 2      |
| Risto Räppääjä ja kauhea makkara | Oodi Library     | 1      |
| Risto Räppääjä ja kauhea makkara | Kallio Library   | 3      |
| Heinähattu ja Vilttitossu        | Pasila Library   | 1      |
| Heinähattu ja Vilttitossu        | Oodi Library     | 0      |
| Heinähattu ja Vilttitossu        | Kallio Library   | 2      |
| Tatu ja Patu Helsingissä         | Pasila Library   | 3      |
| Tatu ja Patu Helsingissä         | Oodi Library     | 2      |
| Tatu ja Patu Helsingissä         | Kallio Library   | 1      |
| Risto Räppääjä saa isän          | Pasila Library   | 2      |
| Risto Räppääjä saa isän          | Oodi Library     | 2      |
| Risto Räppääjä saa isän          | Kallio Library   | 0      |
| Herra Hakkarainen maailmalla     | Pasila Library   | 1      |
| Herra Hakkarainen maailmalla     | Oodi Library     | 3      |
| Herra Hakkarainen maailmalla     | Kallio Library   | 2      |
| Koiramäen talossa                | Pasila Library   | 0      |
| Koiramäen talossa                | Oodi Library     | 2      |
| Koiramäen talossa                | Kallio Library   | 1      |
| Ella ja kaverit salaisessa palveluksessa | Pasila Library   | 3      |
| Ella ja kaverit salaisessa palveluksessa | Oodi Library     | 1      |
| Ella ja kaverit salaisessa palveluksessa | Kallio Library   | 2      |

::::

:::