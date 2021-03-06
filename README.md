
# mementomori 

![Lifecycle
](https://img.shields.io/badge/lifecycle-maturing-blue.svg?style=flat)
![Dependencies
](https://img.shields.io/badge/dependencies-none-brightgreen.svg?style=flat)

mementomori is a python script for reflecting on how many days, weeks, months and years you've been alive
and *approximately* how many more you will live.

If you like mementomori, give it a star, or fork it and contribute!


## Example Output

Age details and life expectancy estimates for _male_ born on 8th January 1992:
```sh
./mementomori -s m -b 1992-01-08

You are 27.36 years old
You are 328.67 months old
You are 1,427.86 weeks old
You are 9,995 days old

You can expect to live approximately 51.74 years
You can expect to live approximately 621.38 months
You can expect to live approximately 2,699.47 weeks
You can expect to live approximately 18,896 days

You are approximately 34.6 % dead
You are approximately 65.4 % alive
```

Age details and life expectancy estimates for _female_ born on 8th January 1992:
```sh
./mementomori -s f -b 1992-01-08

You are 27.36 years old
You are 328.67 months old
You are 1,427.86 weeks old
You are 9,995 days old

You can expect to live approximately 55.44 years
You can expect to live approximately 665.82 months
You can expect to live approximately 2,892.53 weeks
You can expect to live approximately 20,248 days

You are approximately 33.0 % dead
You are approximately 67.0 % alive

```


## Installation

Requires a recent version of python.

Both python versions 2 and 3 are supported.

The following should work on any unix-ish environment:
```sh
wget https://raw.githubusercontent.com/makeyourownmaker/mementomori/master/mementomori
chmod u+x mementomori
./mementomori -h
```


## Details

The mementomori script displays your age in years, months, weeks and days.

It also estimates how much longer you will live based on the 
[National life tables, UK: 2013 to 2015](https://www.ons.gov.uk/peoplepopulationandcommunity/birthsdeathsandmarriages/lifeexpectancies/bulletins/nationallifetablesunitedkingdom/20132015)
from the [Office for National Statistics](https://www.ons.gov.uk/).
There are both male (79.1 years) and female (82.8 years) lifetime estimates.

The script should be run from a daily cron job without the verbose option.
In this case, it only displays ages and lifetime estimates on the following "milestones":
 * every 500 days
 * every 100 weeks
 * every 50 months
 * every 10 years
 * every 10th percentile (10, 20, 30 ... %) of lifetime estimate

Further info:
```sh
./mementomori -h
```

### Command-line options

There are two types of arguments, required and optional.

Required arguments:

| Name       | Short | Long        | Description                       |
|------------|-------|-------------|-----------------------------------|
| Birth date | -b    | --birthdate | Date of birth - format YYYY-MM-DD |

Required but mutually exclusive arguments:

| Name     | Short | Long       | Description                                |
|----------|-------|------------|--------------------------------------------|
| Sex      | -s    | --sex      | Sex; m or M for male and f or F for female |
| Lifetime | -l    | --lifetime | Expected lifetime in years                 |

Either the -l/--lifetime or -s/--sex option is required but both cannot be
used together.

The -l/--lifetime option overrides the default male and female expected
lifetimes.

Optional arguments:

| Name     | Short | Long       | Description                  |
|----------|-------|------------|------------------------------|
| Help     | -h    | --help     | Print help message and exit  |
| Verbose  | -v    | --verbose  | Print additional information |


## Roadmap

 * Check and double-check the milestone calculations
 * Better support males and females who are older than the life expectancy estimates
 * Improve output:
   * Return "x years, y months, z weeks and a days" instead of "42.87 years"
 * New functionality:
   * Add option to print dates for next and/or all future milestone(s)
     * eg 15,000 days old on ...


## Contributing

Pull requests are welcome.  For major changes, please open an issue first to discuss what you would like to change.


## See Also

* [Memento mori on Wikipedia](https://en.wikipedia.org/wiki/Memento_mori)
* [Your Life in Weeks](https://waitbutwhy.com/2014/05/life-weeks.html)
* [The Death Clock](https://www.death-clock.org/)
* [Death Timer](https://www.deathtimer.com/)
* [Find Your Fate Death Clock](https://www.findyourfate.com/deathmeter/deathmtr.html)
* [Adafruit Mindfulness Clock OF DOOM](https://learn.adafruit.com/mindfulness-clock-of-doom)


## License
[GPL-2](https://www.gnu.org/licenses/old-licenses/gpl-2.0.en.html)
