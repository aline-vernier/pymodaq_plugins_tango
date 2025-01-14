pymodaq_plugins_tango
########################

.. the following must be adapted to your developed package, links to pypi, github  description...

.. image:: https://img.shields.io/pypi/v/pymodaq_plugins_template.svg
   :target: https://pypi.org/project/pymodaq_plugins_template/
   :alt: Latest Version

.. image:: https://readthedocs.org/projects/pymodaq/badge/?version=latest
   :target: https://pymodaq.readthedocs.io/en/stable/?badge=latest
   :alt: Documentation Status

.. image:: https://github.com/PyMoDAQ/pymodaq_plugins_template/workflows/Upload%20Python%20Package/badge.svg
   :target: https://github.com/PyMoDAQ/pymodaq_plugins_template
   :alt: Publication Status

.. image:: https://github.com/PyMoDAQ/pymodaq_plugins_template/actions/workflows/Test.yml/badge.svg
    :target: https://github.com/PyMoDAQ/pymodaq_plugins_template/actions/workflows/Test.yml


Use this template to create a repository on your account and start the development of your own PyMoDAQ plugin!


Authors
=======

* Aline Vernier  (aline.vernier@polytechnique.edu)


.. if needed use this field

    Contributors
    ============

    * 

.. if needed use this field

  Depending on the plugin type, delete/complete the fields below


Instruments
===========

Below is the list of instruments included in this plugin

Actuators
+++++++++

* No actuators so far

Viewer0D
++++++++

* No 0D Viewer so far

Viewer1D
++++++++

* Currently developing 1D Viewer for spectrometer


Viewer2D
++++++++

* No 2D Viewer so far


PID Models
==========


Extensions
==========


Installation instructions
=========================

Instrument plugins for stuff on the tango bus
        * Anything on the tango bus can be viewed. Address and attributes should be entered in toml file
        * Tested with TANGO controls on a virtual machine (communication through the virtual switch)
        * PyMoDAQ Version 4.4.7
        * OS : Microsoft 11 Pro 10.0.22631
        * pyTango and tomllib should be installed. To test pyTango install, run the following lines in the CLI
            python
            from tango import DeviceProxy
            tango_host = tango.ApiUtil.get_env_var("TANGO_HOST")
            print(tango_host)
            print(tango.__version__)
        To test communication, run :
            my_device = DeviceProxy(<some known device address, e.g. "SY-SPECTRO_1/Spectrometer/FE1">)
            print(my_device.read_attribute(<some known attribute, e.g. "lambda">).value)
        * The wrapper is in the hardware folder. It uses the tango bus as some sort of virtual hardware.
        This is also where the toml config file is located. It has to be filled for the plugin to work !

    This object inherits all functionalities to communicate with PyMoDAQ’s DAQ_Viewer module through inheritance via
    DAQ_Viewer_base. It makes a bridge between the DAQ_Viewer module and the Python wrapper of a particular instrument.
