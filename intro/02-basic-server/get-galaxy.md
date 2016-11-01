layout: true
class: inverse, middle, large

---
class: special
# How to get Galaxy

slides by @martenson

.footnote[\#usegalaxy / @galaxyproject]

---
class: larger

## Please Interrupt!
Your questions will be answered.

---
class: normal
# Reasons to Install Your Own Galaxy

You only need to download Galaxy if you plan to:

- Run a local production Galaxy because you want to
  - install and use tools unavailable on public Galaxies
  - use sensitive data (e.g. clinical)
  - process large datasets that are too big for public Galaxies
  - plug-in new datasources
- Develop Galaxy tools
- Develop Galaxy itself

---
# Requirements
- UNIX/Linux or Mac OS
- Python 2.7

Optional
  - samtools
  - Git code versioning system
  - GNU Make + gcc to compile and install tool dependencies
  - Additional requirements for shipped tools

---
# Clone the repository
1. check what is the latest [release](https://docs.galaxyproject.org/en/master/releases/index.html)
1. run `$ git clone -b release_16.07 https://github.com/galaxyproject/galaxy.git`
  - you can change `release_16.07` to any release you want

---
# Start Galaxy
1. `$ cd galaxy`
1. `$ ./run.sh`
1. visit `http://localhost:8080`

You now have default Galaxy running.

.footnote[Note that first startup needs internet connection and takes longer than the subsequent ones.]

---
# What happened?

* Galaxy started logging into the terminal from which it is run.
* Galaxy created a Python virtual environment (venv).
* Galaxy fetched needed Python binaries ('wheels') into this environment.
* Galaxy created the default SQLite database and migrated it to the latest version.

???
You can log to a file instead.

---
# Look around

1. Run a basic job (e.g. upload a file).
1. Check `http://localhost:8080/api/version` to see Galaxy's version.
1. Stop Galaxy by terminating the console process.

---
# Basic configuration

- Galaxy works out of the box with default configuration.
- Important config files are in `config/`.
- Galaxy often uses the files with suffix `*.sample` as declared defaults.

---
# Example of configuration change

- By default Galaxy loads all tools in `tool_conf.xml.sample` into toolpanel.
- To add tools you should:
  - Make a copy `$ cp tool_conf.xml.sample tool_conf.xml`.
  - Add your tool entries to the `tool_conf.xml`.
  - Restart Galaxy.

???
Use `<toolbox monitor="true">` to trigger hot reload of tools.

---
# Update the welcome page

Welcome page is `$GALAXY_ROOT/static/welcome.html` and is the first thing that
users see. It is a good idea to extend it with things like:
- Downtimes/Maintenance periods
- New tools
- Publications relating to your Galaxy

No restarting is necessary.

???
You can load remote content to this iframe (blog, existing presentation, etc.).

---
# What to do next?
- Keep your code up to date
- Make yourself an administrator
- Install tools
- Join the mailing list
- Set up a backup process for your instance
- Configure for production