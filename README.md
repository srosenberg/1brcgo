# Billion Row Challenge in Go

Inspired by https://github.com/gunnarmorling/1brc

The challenge is to write a Go program which reads `measurements.txt`,
calculates the min, mean, and max temperature value per weather station, and
emits the results on stdout in the format `<station>=<min>/<mean>/<max>` for
each station, separated by a newline. The stations must be ordered
alphabetically.

The following shows an example of `measurements.txt`:

```
Hamburg;12.0
Bulawayo;8.9
Palembang;38.8
St. John's;15.2
Cracow;12.6
Bridgetown;26.9
Istanbul;6.2
Roseau;34.4
Conakry;31.2
Istanbul;23.0
```

You can generate a sample `measurements.txt` with
`go run generate.go <num-measurement>`.

Once a `measurements.txt` file is created, you can run the sample submission
with `go run baseline.go`.

# Rules

* No external library dependencies may be used
* The computation must happen at application runtime, i.e. you cannot process 
  the measurements file at build time and just bake the result into the binary
* Input value ranges are as follows:
* Station name: non null UTF-8 string of min length 1 character and max 
  length 100 characters
* Temperature value: non null double between -99.9 (inclusive) and 99.9 
  (inclusive), always with one fractional digit
* There is a maximum of 10,000 unique station names
* Implementations must not rely on specifics of a given data set, e.g. any 
  valid station name as per the constraints above and any data distribution
  (number of measurements per station) must be supported

# Submissions

Submit your submission as a PR to this repository by **January 31, 2024**. Your
submission should be a single source file with your name or Github username,
e.g., `alice.go`.

# Evaluation

Submissions will be tested on a Macbook Pro with M1 Pro and 32GB of memory. Go
1.21 will be used. Each submission will compiled and run once to ensure
correctness. Then it will be run five times with the `time` program to track the
runtime. The highest and lowest times will be discarded, and the remaining three
will be averaged for a final result.

# Leaderboard

| Rank | Submission                                                     | Time (seconds) |
|-----:|----------------------------------------------------------------|---------------:|
|    1 | [nvanbenschoten](https://github.com/dhartunian/1brcgo/pull/18) |          1.689 |
|    2 | [pavel](https://github.com/dhartunian/1brcgo/pull/25)          |          1.714 |
|    3 | [jason](https://github.com/dhartunian/1brcgo/pull/19)          |          1.777 |
|    4 | [radu](https://github.com/dhartunian/1brcgo/pull/20)           |          2.165 |
|    5 | [mgartner](https://github.com/dhartunian/1brcgo/pull/7)        |          2.280 |
|    6 | [petermattis](https://github.com/dhartunian/1brcgo/pull/5)     |          3.147 |
|    7 | [arjunmahishi](https://github.com/dhartunian/1brcgo/pull/10)   |          3.467 |
|    - | [baseline.go](baseline.go)                                     |         151.09 |
