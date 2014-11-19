SeaFlowIAAIChallenge
====================

This repository exists to provide instructions and information about the SeaFlow
data association with the IAAI Challenge Paper. This data set contains data from
three relatively small SeaFlow cruises, the Thompson 0, 1, and 10 cruises, respectively.

Each record of the data represents one observed particle (after filtering).
SeaFlow data has the following schema for all particles:
Cruise, Date, File Number, Line Number, Time, Pulse Width, D1, D2, fsc_small, fsc_perp, fsc_big, pe, chl_small, chl_big, pop

See the original SeaFlow paper for a description of all observations: http://www.aslo.org/lomethods/locked/2011/0466.pdf

Here, we break down the most useful columns for analysis:

* Cruise: which cruise this particle came from (i.e. 'Thompson 1')
* Day: string representing date. This is an artifact of how SeaFlow data was previously recorded.
* File Number: string represent file id under date. Again, this is an artificact.
* Line Number: a particle id for a particle under cruise/day/file_id.

The combination cruise/day/file number/line number forms the primary key for a particle.

* fsc_small: forward scatter of a particle
* fsc_perp: perpendicular scatter of a particle
* pe: phycoerythrin measurement of a particle
* chl_small: chlorophyll measurement of a particle

These four dimensions are the measurements typically used to cluster SeaFlow data.

* pop: the hand-labeled population value. This is almost always a string (i.e. 'beads', 'noise', 'nano'),
but because some automation was used in labeling, it is possible that the label will be an integer.
Integer labeled particles can be ignored for testing goodness of a classifier.

Follow the link below for four data sets:

* Thompson 0 data (~1.1GB compressed)
* Thompson 1 data (~600MB compressed)
* Thompson 11 data (~1.1GB compressed)
* Subset of Thompson 1 data for smaller analysis and debugging (41MB compressed)

PROVIDE LINK HERE

NOTE: More SeaFlow data sets (many larger than those provided) are available through the Myria
database at the University of Washington. Many of these data sets have rough labels provided 
by automated methods or no labels at all. Please contact the authors if you would like to 
explore these data sets.
