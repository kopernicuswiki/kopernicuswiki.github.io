---
layout: default
title: LandControl
---

**Example**
```
LandControl
{
	altitudeBlend = 0.1 //How well the different colors blend between transistions over altitude. Larger values result in noisy tranisitions
	altitudeFrequency = 12 //Frequency value
	altitudeOctaves = 2 //Octave value
	altitudePersistance = 0.6 //Altitude Value
	altitudeSeed = 12249
	createColors = True //Whether Land Control should color the terrain or not.
	createScatter = True //Whether Land Control should place terrain scatter
	heightMap = Filepath //Filepath to your planet's heightmap, if any.
	latitudeBlend = 0.1 //How well the different colors blend between transistions over latitude. Larger values result in noisy tranisitions
	latitudeFrequency = 5
	latitudeOctaves = 5
	latitudePersistance = 0.6
	latitudeSeed = 47373
	longitudeBlend = 0.6 //How well the different colors blend between transistions over longitude. Larger values result in noisy tranisitions
	longitudeFrequency = 4
	longitudeOctaves = 4
	longitudePersistance = 0.6
	longitudeSeed = 768453
	useHeightMap = False //Whether the heightmap is used or not
	vHeightMax = 40000 
	order = 999 //Order in which its applied
	enabled = True
	name = _LandClassOcean //Identifier incase of multiple Land Control
	scatters//This node declares all the scatters which can be used on the planet - you must define a scatter here to use in a LandClass
	{
		Value
		{
			materialType = DiffuseWrapped //Can one be of several types
			material = BUILTIN/scatter_rock_kerbin 
			mesh = BUILTIN/boulder //model
			castShadows = True
			densityFactor = 0.25
			maxCache = 512
			maxCacheDelta = 64
			maxLevelOffset = 0
			maxScale = 1.5
			maxScatter = 10
			maxSpeed = 200
			minScale = 0.15 //Size of the scatter
			recieveShadows = True
			name = boulder //Identifier
			seed = 123887
			verticalOffset = -0.25 //How much is it offset in terrain
			instancing = False //Whether they should use instancing or no.
			delete = False
			Material //Material/Texture of the scatter
			{
				mainTex = BUILTIN/rock00
				color = 1,1,1,0.621999979 //Color
				diff = 0.2
			}
		}
	}
	landClasses //This is the section that adds the color and/or scatters to the terrain. Each LandClass is its own Value and is set to a given area by LerpRanges
	{
		Value
		{
			alterApparentHeight = 0 //
			alterRealHeight = 0 //
			color = 0.180000007,0.100000001,0.0700000003,1 //Color of the terrain
			coverageBlend = 1 //Blend of the terrain
			coverageFrequency = 2 //Frequency of coverage
			coverageOctaves = 4 
			coveragePersistance = 0.5
			coverageSeed = 121214
			name = BaseSun //Identifier for the Land Class
			latDelta = 1
			latitudeDouble = True //Whether the LandClass uses latitudeDoubleRange
			lonDelta = 0
			minimumRealHeight = 0
			noiseBlend = 0.5 //How much the noise is blended with terrain color.
			noiseColor = 0.280000001,0.100000001,0.0700000003,1 //Color noise
			noiseFrequency = 8 //Frequency of Noise
			noiseOctaves = 4 //Number of times noise is repeated within itself
			noisePersistance = 0.5
			noiseSeed = 453737
			delete = False
			altitudeRange //Controls Altitude to which the color is applied
			{
				endEnd = 1 //True end - the colors above this land class completely take over.
				endStart = 1 //Start of the end - The color starts fading out, being replaced with colors from other landclasses
				startEnd = -1 //True start. The color now completely covers terrain
				startStart = -1 //Start of color region. The color starts blending with the other land classes below this
			}
			latitudeDoubleRange
			{
				endEnd = 1
				endStart = 1
				startEnd = 0
				startStart = 0
			}
			latitudeRange
			{
				endEnd = 1
				endStart = 1
				startEnd = 0
				startStart = 0
			}
			longitudeRange
			{
				endEnd = 0.5
				endStart = 0.5
				startEnd = 0
				startStart = 0
			}
			scatters//Adds scatters to a give land class
			{
				Value//Each scatter declared in the Scatter node can be used here
				{
					density = 1
					scatterName = boulder //name of the scatter
					delete = False
				}
			}
		}
	}
}
```
