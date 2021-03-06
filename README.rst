================================
  MDAnalysis Repository README
================================

|build| |cov| [*]_

|docs| |devdocs| |usergroup| |developergroup| |anaconda|

MDAnalysis_ is a Python toolkit to analyze molecular dynamics
trajectories generated by a wide range of popular simulation packages
including DL_Poly, CHARMM, Amber, NAMD, LAMMPS, and Gromacs. (See the
lists of  supported `trajectory formats`_ and `topology formats`_.)

.. code:: python

   import MDAnalysis as mda

   # Load simulation results with a single line
   u = mda.Universe('topol.tpr','traj.trr')

   # Select atoms
   ag = u.select_atoms('name OH')

   # Atom data made available as Numpy arrays
   ag.positions
   ag.velocities
   ag.forces

   # Iterate through trajectories
   for ts in u.trajectory:
       print(ag.center_of_mass())

There are also a number of tutorials_ on the MDAnalysis homepage that explain
how to conduct RMSD calculations, Alignment and more features of MDAnalysis.

Source code
===========

Source code is hosted in a git repository at

https://github.com/MDAnalysis/mdanalysis

and is available under the GNU General Public License, version 2 (see
the file LICENSE_).

This is the top level of the master repository. It contains

1. the MDAnalysis toolkit source files in the directory ::

      package/

2. the unit tests together with any input files required for
   running those tests in the directory ::

      testsuite/

The directory ``maintainer`` contains scripts only needed for
maintaining releases and are not generally useful for the user or the
typical developer. The ``vm`` directory contains configurations for
virtual machines.

(For more details on the directory layout see `Issue 87`_ on the
MDAnalysis issue tracker.)

Guide for Developers
====================

To setup a development environment and run the testsuite you can use this
guide_. If you are a new developer who would like to start contributing to
MDAnalysis as a start you can increase our code coverage, the guides explain how
to find uncovered code.

.. Footnotes

.. [*] **build**: Unit testing is for the whole package; **coverage** is
       shown for the core library modules and the analysis modules (which
       excludes `MDAnalysis.visualization`_ at the moment).

.. _trajectory formats: http://docs.mdanalysis.org/documentation_pages/coordinates/init.html#id1
.. _topology formats: http://docs.mdanalysis.org/documentation_pages/topology/init.html#supported-topology-formats
.. _Issue 87: https://github.com/MDAnalysis/mdanalysis/issues/87
.. _MDAnalysis: http://www.mdanalysis.org
.. _LICENSE: https://github.com/MDAnalysis/mdanalysis/blob/master/LICENSE
.. _`#286`: https://github.com/MDAnalysis/mdanalysis/issues/286
.. _`MDAnalysis.analysis`: http://docs.mdanalysis.org/documentation_pages/analysis_modules.html
.. _`MDAnalysis.visualization`: http://docs.mdanalysis.org/documentation_pages/visualization_modules.html
.. _`tutorials`: http://www.mdanalysis.org/pages/learning_MDAnalysis/
.. _`guide`: https://github.com/MDAnalysis/mdanalysis/wiki/Guide-for-Developers

.. |usergroup| image:: https://img.shields.io/badge/Google%20Group-Users-lightgrey.svg
   :alt: User Google Group
   :target: http://users.mdanalysis.org

.. |developergroup| image:: https://img.shields.io/badge/Google%20Group-Developers-lightgrey.svg
   :alt: Developer Google Group
   :target: http://developers.mdanalysis.org

.. |docs| image:: https://img.shields.io/badge/docs-latest-brightgreen.svg
   :alt: Documentation (latest release)
   :target: http://docs.mdanalysis.org

.. |devdocs| image:: https://img.shields.io/badge/docs-development-yellow.svg
   :alt: Documentation (development version)
   :target: http://www.mdanalysis.org/mdanalysis/

.. |build| image:: https://travis-ci.org/MDAnalysis/mdanalysis.svg?branch=develop
    :alt: Build Status
    :target: https://travis-ci.org/MDAnalysis/mdanalysis

.. |cov|   image:: https://coveralls.io/repos/MDAnalysis/mdanalysis/badge.svg?branch=develop
    :alt: Coverage Status
    :target: https://coveralls.io/r/MDAnalysis/mdanalysis?branch=develop

.. |anaconda| image:: https://anaconda.org/mdanalysis/mdanalysis/badges/version.svg
    :alt: Anaconda
    :target: https://anaconda.org/MDAnalysis/mdanalysis
