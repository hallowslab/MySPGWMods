### Dev notes:

Outposts cannot be accessed trough station object, it seems to be a structure however looping trough all structures in the world does not seem to include any of the forward_outposts/Garrison there is also the platform object that does contain keynames like `<FO_123>` that refer to the outposts
```
# Stations.wdt
Id	KeyName	Type
0	SPGW0	Outpost

# MapObjectNames.wdt
Id	KeyName	Name
306	SPGW306	Forward_Outpost

# EditorPlatforms.wdt
Id	KeyName	Name	Schem	File	BoundingSphereRadius	StarchartVisible
1	GARRISON	Forward_Outpost	Data\Models\Platforms\Outpost\schem.dds	Data\Models\Platforms\Outpost\platform.def	550.25	1

# StructureSort.wdt
Id	KeyName	PathToTexture	X	Y	W	H
10	SRT_OUTPOST	Data\Textures\GUIEx\StarchartObjectMarkers.dds	512	640	128	128


# Sector_XYZ.ics
Platform:	
{	
	Model:	GARRISON
	Position:	89226.37	-6000.00	173969.67
	Rotation:	0.00	0.00	0.00
	KeyName:	FO_741
	Faction:	REVENANTS
	ScriptStarchartVisible:	1
	BuildStatus:	2
	BuildLevel:	0
	Controller:	1
}	
```

Parameters that are saved for structures
```
int Condition; // 0. working, 1. dying, 2. broken 3. repair in progress
bool Destructible; // Can it be destroyed?
int Mark; // 0. Off, 1. Main, 2. Side, 3. Random
bool isAditionalParam0Reset; //Shader parameters
```