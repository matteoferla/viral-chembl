# Viral chEMBL
Brief survey of virus binding affinity data and crystallographic data.

## Aim

Hypothesis: there is a lot of data for viral and bacterial targets,
but crystallographic and affinity data is less prevalent, an issue that needs addressing.

## Binding affinity

### Parenthesis: Activity vs binding affinity

Normally Ki or IC50 (inhibition) is normally the preferred metric,
as the aim at the end of the day is to inhibit (most often) the activity.
However, this is measured via a bespoke assay for activity for that enzyme,
namely needs to be set up,
while binding affinity is more generalisable,
and is a measure of a single species binding, not two,
so is better for thermodynamic predictions and high throughput screening.

### Abundance

With the caveat that for non-human entries there is a large `target_id` issue
(see [test-herpesviridales.md](test-herpesviridales.md)),
and the `tax_id` may be patchy,
the number of assays shows that the data we have at hand is severely skewed towards humans.

![k-anything.png](images/k-anything.png)

![kd.png](images/kd.png)

Count of entries (not dedupicated) of top 20 activity types:

| standard_type         |   human |   fungi |   protozoa |   bacteria |   virus |     unknown |
|:----------------------|--------:|--------:|-----------:|-----------:|--------:|------------:|
| Potency               |   69,737 |       0 |          2 |          0 |       0 |   4,403,800 |
| IC50                  |  755,714 |  11,052 |     18,594 |     53,279 |  50,698 |   1,913,560 |
| GI50                  |    2,225 |       0 |          0 |          0 |       0 |   2,621,420 |
| Inhibition            |  318,233 |   6,488 |      7,739 |     22,846 |  14,947 |   1,162,210 |
| Percent Effect        |    8,841 |       0 |          0 |          0 |       0 |   1,319,520 |
| Activity              |  160,991 |   3,046 |      2,078 |     15,420 |   6,631 |   1,093,490 |
| Ki                    |  273,440 |   2,711 |      6,746 |     22,585 |   8,884 |     461,078 |
| MIC                   |       77 |      73 |         12 |      5,958 |      46 |     741,843 |
| EC50                  |   66,778 |     349 |        256 |      1,014 |   7,217 |     447,138 |
| INHIBITION            |        0 |       0 |          0 |          0 |       0 |     339,133 |
| AC50                  |    3,077 |     444 |          0 |        198 |     204 |     274,297 |
| Kd                    |  120,402 |     190 |        330 |      3,179 |   2,202 |      58,695 |
| Z score               |        0 |       0 |          0 |          0 |       0 |     147,592 |
| Ratio IC50            |   51,798 |     190 |        157 |        667 |   1,077 |      81,646 |
| GI                    |      150 |       0 |         10 |         30 |       0 |     129,140 |
| Tissue Severity Score |        0 |       0 |          0 |          0 |       0 |     128,999 |
| Ratio                 |   14,809 |     298 |        530 |      1,819 |   1,272 |     100,493 |
| ED50                  |      535 |       1 |          1 |         33 |      89 |     102,756 |
| CC50                  |      124 |       0 |          0 |         69 |      49 |      98,910 |
| IZ                    |       21 |      91 |          0 |        261 |       0 |      95,631 |

It is clear that problematic entries are problematic for multiple values,
such as ambiguous `standard_type` and missing `assay_tax_id` ("Unknown" in table above).

## Test set: target id issue

The clade Herpesvirales was used as a test case,
however, despite using two datasets mapping ChEMBL to PDB (papyrus and biochemgraph),
no results were found. This included searching for the
known PDB structures with the known inhibitor.
This is possibly because there are different strains making the matches rejected
when the two datasets were made.

A major problem is that the target ID is `Unchecked` (22226) for a large amount of assays.
I believe this is why there is this incongruity.





