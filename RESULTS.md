# pytest benchmark results

Recorded 2026-11-17 (America/New_York) against local checkout `36eed6b7b0eb59760fc4b33e90bdaac5057388f0`.

## Environment

- pytest 10.0.0.dev33+g36eed6b7b
- Python 3.13.5
- argcomplete 3.7.2

## How these were run

From a venv with this checkout and argcomplete installed, in the `bench/` directory:

```bash
# wall time includes both completers; the script also prints each completer's timeit result
/usr/bin/time -f '%e' python bench_argcomplete.py

/usr/bin/time -f '%e' python -m pytest empty.py
/usr/bin/time -f '%e' python -m pytest manyparam.py
/usr/bin/time -f '%e' python -m pytest skip.py
```

`unit_test.py` and `xunit.py` were not part of this run.

## Results

| Bench | Wall time | Detail |
|---|---|---|
| bench_argcomplete | 2.808s | FilesCompleter 2.754s, Fast 0.017s |
| empty | 0.649s | 1000 passed |
| manyparam | 1.050s | 1932 passed |
| skip | 2.804s | 5000 skipped |
