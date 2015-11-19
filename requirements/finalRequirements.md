# Final requirements for m3cfd

## Inputs


### Atmospheric Model

Name| 			Units| 		Comments)
----|----|----
AtmosPressure|	Pa|		Ambient pressure at various altitudes (e.g. International standard atmosphere)
AtmosTemperatre|	K|		Ambient temperature at various altitudes

### Rocket Information


Name| 			Units| 		Comments)
----|----|----
RocketGeometry|	m|		Geometry of the rocket. Will have to consist of multiple STL files as the geometry of the rocket abruptly changes at different points of flight
RocketMass|	kg|		Mass of each geometrical configuration of the rocket in its unloaded state (i.e. no motors). As the variation of mass with time of eah motor will be provided as an input we can work out the overall mass and moment of inertia
RocketMomentInertia|kgm^2|			Moment of inertia in the principal axes of the rocket in its unloaded state.
RocketGeometrySequence| *NA* |		The sequence of the rocket geometries during flight i.e. core+booster, core, dart

### Motor information


Name| 			Units| 		Comments)
----|----|----
ThrustCurve|	N|		Thrust curve of each motor
MassCurve|	kg|		Mass of motor at a given time after motor ignition
MotorLoc|	m|		Location of motor's centre of mass in the rocket. As the motor grains burn radially the centre of mass should remain constant

### Initial conditions

Name| 			Units| 		Comments)
----|----|----
InitialVelocity|	m/s|		Initial velocity vector of the rocket
InitialASL|	m|		Initial altitude of rocket above sea level
InitialAlpha|	degrees|		Initial angle of attack from rocket

### Fin material

Name| 			Units| 		Comments)
----|----|----
YoungsModulus|	Pa|		Stiffness of fins


## Outputs

Name| 			Units| 		Comments)
----|----|----
FlightPath|	m|		Altitude of rocket vs time
FlightSpeed|		m/s|		Speed of rocket vs time
FlightAlpha|	degrees|		Angle of attack of rocket vs time. (from the above three we should be able to recreate that moment of flight by plugging it into the minimum viable product)
MaxLoading|	Pa|		Map of maximum pressures each point experiences during flight? (Not sure what is most helpful for mechanical team)
MaxTemperature|	K|		Map of maximum temperature over rocket surface
FlutterOcurred|	bool|		Whether fin flutter occurred during the flight
FlutterTime|	s|		Time at which flutter occurred
