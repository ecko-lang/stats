# stats

Descriptive statistics for [Ecko](https://ecko.sh), written in Ecko. Pure - no
capabilities.

## Install

```bash
ecko get github.com/ecko-sh/stats
```

## Usage

```ecko
import stats

stats.mean([2, 4, 6])        # 4.0
stats.median([1, 2, 3, 4])   # 2.5
stats.mode([1, 2, 2, 3])     # 2
stats.stdev(samples)         # sample standard deviation
stats.quantile(xs, 0.95)     # 95th percentile
stats.range_of([3, 7, 1])    # 6
```

## API

| Function | Description |
|---|---|
| `mean(xs)` | Arithmetic mean |
| `median(xs)` | Middle value (mean of the two middle for even length) |
| `mode(xs)` | Most frequent value; smallest on a tie |
| `variance(xs)` / `stdev(xs)` | Sample variance / standard deviation (n − 1) |
| `pvariance(xs)` / `pstdev(xs)` | Population variance / standard deviation (n) |
| `quantile(xs, q)` | The q-th quantile (q in 0..1), linear interpolation |
| `range_of(xs)` | `max − min` |

Integer inputs are promoted to floats where a ratio is involved, so results
never silently truncate. An empty list (or `< 2` values for sample variance)
raises a kind-`"value"` error.

## Testing

```bash
ecko test tests/
```

## License

MIT - see [LICENSE](LICENSE).
