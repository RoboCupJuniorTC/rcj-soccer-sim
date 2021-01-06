# RCJ Soccer Simulator

This is the official repository of the RoboCupJunior Soccer Simulator. The
simulator is based on [Webots](https://github.com/cyberbotics/webots) and this
repository provides both the "automatic referee" (which implements the [Soccer
Simulated Rules](https://github.com/RoboCupJuniorTC/soccer-rules-simulation))
as well as a sample simulated team of robots with some basic strategy.

![Soccer Sim](./docs/docs/images/soccer_sim.png)

*Learn more in the [documentation](https://robocupjuniortc.github.io/rcj-soccer-sim/).*

## How do I try this out?

1. Download [Webots](https://www.cyberbotics.com/#download)

2. Clone this repository to your computer by downloading the ZIP file from [here](https://github.com/RoboCupJuniorTC/rcj-soccer-sim/archive/master.zip) or running

        git clone https://github.com/RoboCupJuniorTC/rcj-soccer-sim.git

3. Soccer Sim needs Python version 3.7 (or higher). You can download it from [here](https://www.python.org/downloads/).

4. In Webots, go to `Tools > Preferences > Python command` and set it to `python` or `python3` to point Webots to Python 3. Depending on your system, the reference to Python 3 can be via the command `python` or `python3`. More information on how to configure Webots to work with Python can be found [here](https://cyberbotics.com/doc/guide/using-python).

5. Use Webots to open the downloaded `soccer.wbt` world located in the `worlds`
   directory (via `File > Open World`)

6. Run the simulation. Note that the controllers that are responsible for the
   various robots on the field can be found in the `controllers/` directory.

## Notes

A specific `webots` world can be executed directly from the command line as
follows:

        webots --mode=run worlds/soccer.wbt

Which allows for at least some automation. Further info can be found in the
[docs](https://cyberbotics.com/doc/guide/starting-webots).

The sample players as well as the "automatic referee" are implemented in
Python, which should allow for easily updating the code to match the rules and
avoid any compilation issues.

## Development

We are open to contributions! Have a look at our [issues](https://github.com/RoboCupJuniorTC/rcj-soccer-sim/issues).
Before you make a pull request, make sure the code is formatted
with `black` and `isort`, and `flake8` issues are fixed.

To do so, follow these steps:

1. Create virtualenv `virtualenv -p python3 venv`
2. Install development modules `pip install -r requirements/development.txt`
3. Setup pre-commit hook `pre-commit install`. This hook will not allow you to commit in case one of
the checkers raises an error.
4. In order format the code, run the formatters in this order
    * `isort .`
    * `black .`
5. Manually fix error raised by `flake8 .`

    