.. image:: https://img.shields.io/badge/dmtn--194-lsst.io-brightgreen.svg
   :target: https://dmtn-194.lsst.io
.. image:: https://github.com/lsst-dm/dmtn-194/workflows/CI/badge.svg
   :target: https://github.com/lsst-dm/dmtn-194/actions/

################################################################
Moving toward a simplified objective function for scarlet models
################################################################

DMTN-194
========

Science pipelines made meas_extensions_scarlet the default deblender for multi-band deblending in weekly w_2021_05, which is powered by the scarlet package. scarlet was co-created by science pipelines and Peter Melchior's group at Princeton with the dual goal of deblending multi-band images in HSC/Rubin Observatory data and future joint processing with a fusion of observations from both ground and space-based telescopes as well as other instruments like IFUs and grisms. As scarlet has become an increasingly more powerful tool, the chain of classes and commands required to build the objective function has become increasingly complex in order to properly handle the wide variety of applications that scarlet supports (both now and in the near future). This technote describes the current complexity of scarlet models, the subset of those models actually used in the science pipelines, and a proposal for using a more simple model in meas_extensions_scarlet to potentially speed up development, runtime, and improve the memory footprint.

Links
=====

- Live drafts: https://dmtn-194.lsst.io
- GitHub: https://github.com/lsst-dm/dmtn-194

Build
=====

This repository includes lsst-texmf_ as a Git submodule.
Clone this repository::

    git clone --recurse-submodules https://github.com/lsst-dm/dmtn-194

Compile the PDF::

    make

Clean built files::

    make clean

Updating acronyms
-----------------

A table of the technote's acronyms and their definitions are maintained in the ``acronyms.tex`` file, which is committed as part of this repository.
To update the acronyms table in ``acronyms.tex``::

    make acronyms.tex

*Note: this command requires that this repository was cloned as a submodule.*

The acronyms discovery code scans the LaTeX source for probable acronyms.
You can ensure that certain strings aren't treated as acronyms by adding them to the `skipacronyms.txt <./skipacronyms.txt>`_ file.

The lsst-texmf_ repository centrally maintains definitions for LSST acronyms.
You can also add new acronym definitions, or override the definitions of acronyms, by editing the `myacronyms.txt <./myacronyms.txt>`_ file.

Updating lsst-texmf
-------------------

`lsst-texmf`_ includes BibTeX files, the ``lsstdoc`` class file, and acronym definitions, among other essential tooling for LSST's LaTeX documentation projects.
To update to a newer version of `lsst-texmf`_, you can update the submodule in this repository::

   git submodule update --init --recursive

Commit, then push, the updated submodule.

.. _lsst-texmf: https://github.com/lsst/lsst-texmf
