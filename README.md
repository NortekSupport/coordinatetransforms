# coordinatetransforms
Scripts for coordinate transforms on data from Nortek instruments.

## Background ##
All Nortek instruments collect velocity data in a coordinate system. The most raw form of the data is BEAM coordinates, where the velocity measurement is a vector in the direction of the transducer beam. Beam coordinates can be converted to a Cartesian coordinate system (XYZ) by knowing the beam orientation. Furthermore, the flow can be presented in Earth normal coordinates (ENU, East, North and Up) if the instrument is equipped with a compass and tilt sensor. ENU and XYZ coordinates are the most practical when handling data. Beam coordinates are primarily useful for higher-level turbulence calculations and for dealing with phase wrapping issues.

The coordinate systems are defined as follows:
- In Beam coordinates, a positive velocity is directed in the same direction as the beam points. Beam 1 is marked with an “X” on the head.
- In XYZ coordinates, a positive velocity in the X-direction goes in the direction of the X-axis arrow. The X-axis points in the same direction as beam 1. Use the right-hand-rule to remember the notation conventions for vectors. Remember that XYZ coordinates are relative to the probe/instrument head and independent of whether the instrument points up or down. When you collect data in XYZ coordinates Y is reported as 0° and X is reported as 90°.
- In ENU coordinates, a positive east velocity goes toward east. This is also a right-handed orthogonal system. When you collect data in ENU coordinates N is reported as 0° and E is reported as 90°.

![image](https://user-images.githubusercontent.com/90250703/133058730-67a672ff-80c4-4eef-8ae5-3ae340fb3b56.png)

## The scripts ##
- Sig4beam_transform.m - Comprehensive Matlab script for transforming 4-beam Signature data from BEAM to XYZ or ENU coordinates, and between all coordinate systems. Requires little editing.
- Transform.m - The original transformation Matlab script containing the required steps for transforming data from a 3-beam midlife Nortek instrument from BEAM to XYZ or ENU coordinates, and between all coordinate systems. Requires work from the user to tailor the script to their own instrument/data.
