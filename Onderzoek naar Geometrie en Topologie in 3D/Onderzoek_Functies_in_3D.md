# 3D Functies en topologie in implementaties

Onderstaande tabellen tonen een overzicht van functies die men kan uitvoeren met 2D en/of 3D geometrie. De functies zijn verdeeld in een aantal thema's: 
- formatting functions 
- convert geometries functions
- create geometries functions
- edit geometries functions
- topologische relations functions
- measure functions
- count functions
- properties functions
- topografie functions
- triangulaties functions
- overig functions

Het biedt een overzicht van mogelijkheden en verschillen tussen 2D en 3D functies in verschillende omgevingen. Zo ondersteunt PostGIS zowel een ST_Distance als een ST_3DDistance functie, terwijl GeoSPARQL alleen geof:distance kent.

Door de functies en de geometrie te kennen wordt inzichtelijk welke geometrische operaties tussen GIS en BIM exact of alleen benaderd overdraagbaar zijn. Daarnaast maakt het overzicht het mogelijk om te bepalen welke definitie van ruimtelijke afstand wordt gehanteerd bij heterogene datasets, zoals de afstand tussen een 3D BIM-gebouw en een 2D GIS-object. Afhankelijk van de gekozen functie (bijvoorbeeld 2D of 3D distance-operaties) kan dezelfde situatie tot verschillende uitkomsten leiden, wat de semantische afhankelijkheid van geometrische operaties onderstreept.

## Functions: 

### Formatting functions

| GeoSPARQL | PostGIS | H2GIS | Spatialite |
|-----------|---------|--------|------------|
| geof:asGeoJSON | [st_asgeojson](https://postgis.net/docs/ST_AsGeoJSON.html) | [ST_AsGeoJson](https://h2gis.readthedocs.io/en/latest/ST_AsGeoJson.html) | asgeojson |
| geof:asGML | [st_asgml](https://postgis.net/docs/ST_AsGML.html) | [st_asgml](https://h2gis.readthedocs.io/en/latest/ST_AsGML.html) | asgml |
| geof:asKML | [st_askml](https://postgis.net/docs/ST_AsKML.html) | [ST_AsKML](https://h2gis.readthedocs.io/en/latest/ST_AsKML.html) | askml |
| geof:asWKT |         | st_aswkt | aswkt |
| geof:asEWKB | [st_asewkb](https://postgis.net/docs/ST_AsEWKB.html) | [AsEWKB](https://h2gis.readthedocs.io/en/latest/ST_AsEWKB.html) | asewkb |
|             | [st_ashexewkb](https://postgis.net/docs/ST_AsHEXEWKB.html) |        |            |
|             | [ST_AsX3D](https://postgis.net/docs/ST_AsX3D.html) |        | asx3d      |
|             | st_asewkt |        | asewkt     |
|             | st_assvg  |        | assvg      |
|             | st_astext | st_astext | astext  |
|             |           |        | astwkb     |
|             | [st_asbinary](https://postgis.net/docs/ST_AsBinary.html) | st_asbinary | asbinary |
| geof:asDGGS |           |        |            |
| geof:asGeocode |        |        |            |
|             |           |        | asfgf      |
|             |           |        | asgpb      |
|             |           |        | asencodedpolyline |
|             |           |        | atm_astext |
|             |           |        | gcp_astext |
|             |           |        | proj_asprojstring |
|             |           |        | proj_aswkt |

### Convert geometries

| GeoSPARQL | PostGIS | H2GIS | Spatialite |
|-----------|---------|--------|------------|
|           | [st_Force2d](https://postgis.net/docs/ST_Force2D.html) | st_force2d |            |
|           | [st_ForceCurve](https://postgis.net/docs/ST_ForceCurve.html) |        |            |
|           | [st_force_3d](https://postgis.net/docs/ST_Force_3D.html) | [st_force3d](https://h2gis.readthedocs.io/en/latest/ST_Force3D.html) |            |
|           | st_force_3dm | [st_force3dm](https://h2gis.readthedocs.io/en/latest/ST_Force3DM.html) |            |
|           | [st_force_3dz](https://postgis.net/docs/ST_Force_3DZ.html) |        |            |
|           | [st_force_4d](https://postgis.net/docs/ST_Force_4D.html) | [st_Force4D](https://h2gis.readthedocs.io/en/latest/ST_Force4D.html) |            |
|           | [st_force_collection](https://postgis.net/docs/ST_Force_Collection.html) |        |            |
|           |         |        | forceasnull |
|           | [st_forcerhr](https://postgis.net/docs/ST_ForceRHR.html) |        |            |
|           | [CG_ForceLHR](https://postgis.net/docs/CG_ForceLHR.html) |        | forcelhr   |
|           | [st_forcerSFS](https://postgis.net/docs/ST_ForceSFS.html) |        |            |
|           | [ForcePolygonCCW](https://postgis.net/docs/ST_ForcePolygonCCW.html) |        | forcepolygonccw |
|           | [ForcePolygonCW](https://postgis.net/docs/ST_ForcePolygonCW.html) |        | forcepolygoncw |
|           |         |        | normalizelonlat |
|           |         |        | project     |
|           |         |        | spatnetfromgeom |
|           |         |        | spatnetfromtgeo |
|           |         |        | sridfromauthcrs |
|           | [st_shift_longitude](https://postgis.net/docs/ST_ShiftLongitude.html) |        | st_shift_longitude |
|           | st_wkbtosql |        | st_wkbtosql |
|           | st_wkttosql |        | st_wkttosql |
|           |         |        | tinypointencode |
|           |         |        | togars      |
|           |         |        | uncompressgeometry |
|           |         |        | xb_getgeometry |
|           |         | st_projectpoint |        |
|           |         | st_tomultipoint |        |
|           |         | st_tomultisegments |     |
|           | [st_curvetoline](https://postgis.net/docs/ST_CurveToLine.html) |        |            |
|           | st_geogfromtext |        |            |
|           | st_geogfromwkb |        |            |
|           | st_geographyfromtext |  |            |
|           | st_geometryfromtext |   |            |
|           | st_gmltosql |        |            |
|           | st_linefromwkb |     |            |
|           | st_linestringfromwkb | |            |
|           | [st_linetocurve](https://postgis.net/docs/ST_LineToCurve.html) |        |            |

### Create geometries

| GeoSPARQL | PostGIS | H2GIS | Spatialite |
|-----------|---------|--------|------------|
|           | st_extrude | [st_extrude](https://h2gis.readthedocs.io/en/latest/ST_Extrude.html) |            |
|           | [CG_Extrude](https://postgis.net/docs/CG_Extrude.html) |        |            |
|           |           | [st_geometryshadow](https://h2gis.readthedocs.io/en/latest/ST_GeometryShadow.html) |            |
| geof:boundary | [st_boundary](https://postgis.net/docs/ST_Boundary.html) | st_boundary | boundary |
| geof:boundingCircle |        | st_boundingcircle |            |
|           | [st_BoundingDiagonal](https://postgis.net/docs/ST_BoundingDiagonal.html) |        |            |
|           | st_minimumboundingcircle |        |            |
| geof:concaveHull |        |        | concavehull |
| geof:convexHull | [st_convexhull](https://postgis.net/docs/ST_ConvexHull.html) | st_convexhull | convexhull |
|           | [CG_3DConvexHull](https://postgis.net/docs/CG_3DConvexHull.html) |        |            |
| geof:difference | [st_difference](https://postgis.net/docs/ST_Difference.html) | st_difference | difference |
|           | [CG_3DDifference](https://postgis.net/docs/CG_3DDifference.html) |        |            |
| geof:envelope | st_envelope | st_envelope | envelope |
| geof:symDifference | [st_symdifference](https://postgis.net/docs/ST_SymDifference.html) | st_symdifference | symdifference |
| geof:union | [st_union](https://postgis.net/docs/ST_Union.html) | st_union | gunion |
|           | [CG_3DUnion](https://postgis.net/docs/CG_3DUnion.html) |        |            |
| geof:patchN | [st_PatchN](https://postgis.net/docs/ST_PatchN.html) |        |            |
|           | [CG_MakeSolid](https://postgis.net/docs/CG_MakeSolid.html) |        |            |
|           | [ST_LineSubstring](https://postgis.net/docs/ST_LineSubstring.html) |        |            |
|           |           |        | atm_create |
|           |           |        | atm_createrotate |
|           |           |        | atm_createscale |
|           |           |        | atm_createtranslate |
|           |           |        | atm_createxroll |
|           | st_bdmpolyfromtext |        | bdmpolyfromtext |
|           |           |        | bdmpolyfromwkb |
|           | st_bdpolyfromtext |        | bdpolyfromtext |
|           |           |        | bdpolyfromwkb |
|           |           |        | blobfromfile |
|           | st_buildarea |        | buildarea |
|           |           |        | buildcirclembr |
|           |           |        | buildmbr |
|           |           |        | castautomagic |
|           |           |        | casttoblob |
|           |           |        | casttodouble |
|           |           |        | casttogeometycollection |
|           |           |        | casttointeger |
|           |           |        | casttolinestring |
|           |           |        | casttomulti |
|           |           | st_tomultiline | casttomultilinestring |
|           |           |        | casttomultipoint |
|           |           |        | casttomultipolygon |
|           |           |        | casttopoint |
|           |           |        | casttopolygon |
|           |           |        | casttosingle |
|           |           |        | casttotext |
|           |           |        | casttoxy |
|           |           |        | casttoxym |
|           |           |        | casttoxyz |
|           |           |        | casttoxyzm |
|           | [st_collect](https://postgis.net/docs/ST_Collect.html) | st_collect | collect |
|           | st_collectionextract | st_collectionextract | collectionextract |
|           |           |        | createnetwork |
|           |           |        | createroutingnodes |
|           |           |        | createtopogeo |
|           |           |        | createtopology |
|           |           |        | dissolvepoints |
|           |           |        | dissolvesegments |
|           |           |        | elementarygeometries |
|           |           |        | extractmultilinestring |
|           |           |        | extractmultipoint |
|           |           |        | extractmultipolygon |
|           |           |        | geomcollfromtext |
|           |           |        | geomcollfromwkb |
|           |           |        | geometrycollectionfromtext |
|           |           |        | geometrycollectionfromwkb |
|           |           |        | geometrypointencode |
|           | [st_geomfromewkb](https://postgis.net/docs/ST_GeomFromEWKB.html) |        | geomfromewkb |
|           | [st_geomfromewkt](https://postgis.net/docs/ST_GeomFromEWKT.html) |        | geomfromewkt |
|           |           |        | geomfromexifgpsblob |
|           |           |        | geomfromfgf |
|           | [st_GeomFromGeoJSON](https://postgis.net/docs/ST_GeomFromGeoJSON.html) |        | geomfromgeojson |
|           | [st_geomfromgml](https://postgis.net/docs/ST_GeomFromGML.html) | st_geomfromgml | geomfromgml |
|           |           |        | geomfromgpb |
|           | [st_geomfromkml](https://postgis.net/docs/ST_GeomFromKML.html) |        | geomfromkml |
|           | st_geomfromtext | st_geomfromtext | geomfromtext |
|           | st_geomfromwkb | st_geomfromwkb | geomfromwkb |
|           |           |        | geosconcavehull |
|           |           |        | gpkgmakepoint |
|           |           |        | gpkgmakepointm |
|           |           |        | gpkgmakepointz |
|           |           |        | gpkgmakepointzm |
|           |           |        | gunion |
|           |           |        | hexagonalgrid |
|           |           |        | hilbertcode |
|           |           |        | linefromencodedpolyline |
|           | st_linefromtext | st_linefromtext | linefromtext<br>linestringfromtext |
|           |           |        | linefromwkb<br>linestringfromwkb |
|           |           |        | linesfromrings |
|           |           |        | linestringfromtext |
|           |           |        | linestringfromwkb |
|           |           |        | makearc |
|           |           |        | makecircle |
|           |           |        | makecircularsector |
|           |           |        | makecircularstripe |
|           |           | st_makeellipse | makeellipse |
|           |           |        | makeellipticarc |
|           |           |        | makeellipticsector |
|           | [st_makeline](https://postgis.net/docs/ST_MakeLine.html) | st_makeline | makeline |
|           | [st_makepoint](https://postgis.net/docs/ST_MakePoint.html) | st_makepoint | makepoint |
|           | st_makepointm |        | makepointm |
|           |           |        | makepointz |
|           |           |        | makepointzm |
|           | [st_makepolygon](https://postgis.net/docs/ST_MakePolygon.html) | st_makepolygon | makepolygon |
|           |           |        | mlinefromtext |
|           |           |        | mlinefromwkb |
|           |           |        | mpointfromtext |
|           | st_mpointfromtext | st_mpointfromtext | mpointfromtext<br>multipointfromtext |
|           |           |        | mpointfromwkb<br>multipointfromwkb |
|           |           |        | mpolyfromtext |
|           |           |        | mpolyfromwkb |
|           |           |        | multilinestringfromtext |
|           |           |        | multilinestringfromwkb |
|           |           |        | multipolygonfromtext |
|           |           |        | multipolygonfromwkb |
|           |           |        | orientedenvelope |
|           | st_pointfromtext | st_pointfromtext | pointfromtext |
|           | [st_pointfromwkb](https://postgis.net/docs/ST_PointFromWKB.html) | st_pointfromwkb | pointfromwkb |
|           | [st_pointonsurface](https://postgis.net/docs/ST_PointOnSurface.html) | st_pointonsurface | pointonsurface |
|           |           |        | polyfromtext |
|           |           |        | polyfromwkb |
|           |           |        | polygonfromtext |
|           |           |        | polygonfromwkb |
|           | st_polygonize | st_polygonize | polygonize |
|           |           |        | squaregrid |
|           | [st_point](https://postgis.net/docs/ST_Points.html) | st_point | st_point |
|           |         |        | topogeo_polygonize |
|           |         |        | triangulargrid |
|           |         |        | voronojdiagram |
|           |         | st_isovist |            |
|           |         | st_linefromwkb |        |
|           |         | st_makeenvelope |       |
|           |         | st_makegrid |           |
|           |         | st_makegridpoints |     |
|           |         | st_minimumrectangle |   |
|           | st_mlinefromtext | st_mlinefromtext | |
|           | st_mpolyfromtext | st_mpolyfromtext | |
|           |         | st_octogonalenvelope |   |
|           | st_polygonfromtext | st_polyfromtext | |
|           |         | st_polyfromwkb |         |
|           |         | st_ringbuffer |          |
|           |         | st_ringsidebuffer |      |
|           |         | st_sidebuffer |          |
|           |         | [st_tessellate](https://h2gis.readthedocs.io/en/latest/ST_Tesselate.html) | |
|           | [CG_Tesselate](https://postgis.net/docs/CG_Tesselate.html) |        | |
|           | [st_linefrommultipoint](https://postgis.net/docs/ST_LineFromMultiPoint.html) | | |
|           | st_makebox2d |        | |
|           | st_makebox3d |        | |
|           | st_makeenvelope |     | |
|           | st_multi |            | |
|           | [st_polygon](https://postgis.net/docs/ST_Polygon.html) | | |

### Edit geometries 

| GeoSPARQL | PostGIS | H2GIS | Spatialite |
|-----------|---------|--------|------------|
|           |         | [st_addz](https://h2gis.readthedocs.io/en/latest/ST_AddZ.html) |            |
|           | [AddGeometryColumn](https://postgis.net/docs/AddGeometryColumn.html) |        | addgeometrycolumn |
|           | [st_addmeasure](https://postgis.net/docs/ST_AddMeasure.html) |        | addmeasure |
|           | [st_addpoint](https://postgis.net/docs/ST_AddPoint.html) | st_addpoint | addpoint |
|           |         |        | addedgemodface |
|           |         |        | addedgenewfaces |
|           |         |        | addfdogeometrycolumn |
|           | [DropGeometryColumn](https://postgis.net/docs/DropGeometryColumn.html) | | |
|           |         |        | addisoedge |
|           |         |        | addisonetnode |
|           |         |        | addisonode |
|           |         |        | addlink |
|           |         |        | addtemporarygeometrycolumn |
|           |         |        | gpkgaddgeometrycolumn |
|           |         |        | gpkgaddgeometrytriggers |
|           |         |        | gpkgaddspatialindex |
|           |         |        | gpkgaddtiletriggers |
|           |         |        | topogeo_addlinestring |
|           |         |        | topogeo_addlinestringnoface |
|           |         |        | topogeo_addpoint |
|           |         |        | xb_addfileid |
|           |         |        | xb_addparentid |
|           |         | [st_interpolate3dline](https://h2gis.readthedocs.io/en/latest/ST_Interpolate3DLine.html) | |
|           | [ST_InterpolatePoint](https://postgis.net/docs/ST_InterpolatePoint.html) | | interpolatepoint |
|           | [ST_LineInterpolatePoint](https://postgis.net/docs/ST_LineInterpolatePoint.html) | | |
|           | [ST_LineInterpolatePoints](https://postgis.net/docs/ST_LineInterpolatePoints.html) | | |
|           | [ST_3DLineInterpolatePoint](https://postgis.net/docs/ST_3DLineInterpolatePoint.html) | | |
|           |         |        | line_interpolate_equidistant_points |
|           | st_line_interpolate_point | | line_interpolate_point |
|           |         |        | trajectoryinterpolatepoint |
|           |         | [st_multiplyz](https://h2gis.readthedocs.io/en/latest/ST_MultiplyZ.html) | |
|           | [st_reverse](https://postgis.net/docs/ST_Reverse.html) | st_reverse | reverse |
|           |         | [st_reverse3dline](https://h2gis.readthedocs.io/en/latest/ST_Reverse3DLine.html) | |
|           | [UpdateGeometrySRID](https://postgis.net/docs/UpdateGeometrySRID.html) | | |
| geof:buffer | st_buffer | st_buffer | buffer |
| geof:transform | st_transform | st_transform | transform |
| geof:metricBuffer | | | |
| geof:transformCRS84 | | | |
|           | [CG_ChaikinWmooting](https://postgis.net/docs/ST_ChaikinSmoothing.html) | | |
|           | [ST_Scroll](https://postgis.net/docs/ST_Scroll.html) | | |
|           | [ST_WrapX](https://postgis.net/docs/ST_WrapX.html) | | |
|           |         |        | atm_invert |
|           |         |        | atm_multiply |
|           |         |        | atm_rotate |
|           |         |        | atm_scale |
|           |         |        | atm_transform |
|           |         |        | atm_translate |
|           | st_expand | st_expand | expand |
|           |         |        | gcp_transform |
|           |         |        | geosdensify |
|           |         |        | geosmakevalid |
|           | st_line_substring | | line_substring |
|           | st_linemerge | st_linemerge | linemerge |
|           | [st_makevalid](https://postgis.net/docs/ST_MakeValid.html) | st_makevalid | makevalid |
|           |         |        | makevaliddiscarded |
|           |         |        | reduceprecision |
|           |         |        | reflectcoordinates |
|           |         |        | sanitizegeometry |
|           | st_segmentize | | segmentize |
|           | [st_setpoint](https://postgis.net/docs/ST_SetPoint.html) | | setpoint |
|           | st_simplify | st_simplify | simplify |
|           | [CG_Simplify](https://postgis.net/docs/CG_Simplify.html) | | |
|           | st_simplifypreservetopology | st_simplifypreservetopology | simplifypreservetopology |
|           |         | st_snap | snap |
|           | [st_snaptogrid](https://postgis.net/docs/ST_SnapToGrid.html) | | snaptogrid |
|           |         | st_split | split |
|           | [st_node](https://postgis.net/docs/ST_Node.html) | st_node | st_node |
|           | [st_translate](https://postgis.net/docs/ST_Translate.html) | st_translate | st_translate |
|           | [CG_3DTranslate](https://postgis.net/docs/CG_3DTranslate.html) | | |
|           | [swapordinates](https://postgis.net/docs/ST_SwapOrdinates.html) | | |
|           | [st_UnaryUnion](https://postgis.net/docs/ST_UnaryUnion.html) | | unaryunion |
|           |         | st_densify | |
|           |         | st_explode | |
|           | [ST_FlipCoordinates](https://postgis.net/docs/ST_FlipCoordinates.html) | st_flipcoordinates | |
|           |         | st_normalize | |
|           |         | st_precisionreducer | |
|           |         | st_removeduplicatedcoordinates | |
|           | [ST_RemoveRepeatedPoints](https://postgis.net/docs/ST_RemoveRepeatedPoints.html) | st_removerepeatedpoints | |
|           | [st_rotate](https://postgis.net/docs/ST_Rotate.html) | st_rotate | |
|           | [CG_3DRotate](https://postgis.net/docs/CG_3DRotate.html) | | |
|           | [st_rotatex](https://postgis.net/docs/ST_RotateX.html) | | |
|           | [CG_RotateX](https://postgis.net/docs/CG_RotateX.html) | | |
|           | [CG_RotateY](https://postgis.net/docs/CG_RotateY.html) | | |
|           | [CG_RotateZ](https://postgis.net/docs/CG_RotateZ.html) | | |
|           | [st_rotatey](https://postgis.net/docs/ST_RotateY.html) | | |
|           | [st_rotatez](https://postgis.net/docs/ST_RotateZ.html) | | |
|           | [st_scale](https://postgis.net/docs/ST_Scale.html) | st_scale | |
|           | [CG_3DScale](https://postgis.net/docs/CG_3DScale.html) | | |
|           | [CG_3DScaleAroundCenter](https://postgis.net/docs/CG_3DScaleAroundCenter.html) | | |
|           | [st_affine](https://postgis.net/docs/ST_Affine.html) | | |
|           | [st_dump](https://postgis.net/docs/ST_Dump.html) | | |
|           | [st_DumpPoints](https://postgis.net/docs/ST_DumpPoints.html) | | |
|           | [st_dumprings](https://postgis.net/docs/ST_DumpRings.html) | | |
|           | [st_dumpsegments](https://postgis.net/docs/ST_DumpSegments.html) | | |
|           | [st_memunion](https://postgis.net/docs/ST_MemUnion.html) | | |
|           | [st_transscale](https://postgis.net/docs/ST_TransScale.html) | | |


### Topological Relations

| GeoSPARQL | PostGIS | H2GIS | Spatialite |
|-----------|---------|--------|------------|
| geof:sfContains | st_contains | st_contains | contains |
| geof:ehCoveredBy | st_coveredby | | coveredby |
| geof:ehCovers | st_covers | st_covers | covers |
| geof:sfCrosses | st_crosses | st_crosses | crosses |
| geof:sfDisjoint | st_disjoint | st_disjoint | mbrdisjoint |
| geof:sfEquals | st_equals | st_equals | equals |
|             | [TG_Equals](https://postgis.net/docs/TG_Equals.html) | | |
| geof:intersection | [st_intersection](https://postgis.net/docs/ST_Intersection.html) | st_intersection | intersection |
|             | [CG_3DIntersection](https://postgis.net/docs/CG_3DIntersection.html) | | |
| geof:sfIntersects | st_intersects | st_intersects | intersects |
|             | [tg_intersects](https://postgis.net/docs/TG_Intersects.html) | | |
|             | [ST_3DIntersects](https://postgis.net/docs/ST_3DIntersects.html) | | |
| geof:sfOverlaps | st_overlaps | st_overlaps | overlaps |
|             | [&&&](https://postgis.net/docs/geometry_overlaps_nd.html) | | |
|             | [&&&(geometry,gidx)](https://postgis.net/docs/overlaps_nd_geometry_gidx.html) | | |
|             | [&&&(gidx, geometry)](https://postgis.net/docs/overlaps_nd_gidx_geometry.html) | | |
|             | [&&&(gidx,gidx)](https://postgis.net/docs/overlaps_nd_gidx_gidx.html) | | |
| geof:sfTouches | st_touches | st_touches | touches |
| geof:sfWithin | st_within | st_within | within |
|             | st_dfullywithin | | |
|             | [st_3DDFullyWithin](https://postgis.net/docs/ST_3DDFullyWithin.html) | | |
| geof:ehContains | | | |
| geof:ehDisjoint | | | |
| geof:ehEquals | | | |
| geof:ehInside | | | |
| geof:ehMeet | | | |
| geof:ehOverlap | | | |
| geof:rcc8dc | | | |
| geof:rcc8ec | | | |
| geof:rcc8eq | | | |
| geof:rcc8ntpp | | | |
| geof:rcc8ntppi | | | |
| geof:rcc8po | | | |
| geof:rcc8tpp | | | |
| geof:rcc8tppi | | | |
| geof:relate | st_relate | st_relate | relate |
|             | [st_CPAWithin](https://postgis.net/docs/ST_CPAWithin.html) | | |
|             |         |        | buildmbrfilter |
|             | st_closestpoint | st_closestpoint | closestpoint |
|             | [ST_ClosestPointOfApproach](https://postgis.net/docs/ST_ClosestPointOfApproach.html) | | |
|             | [ST_3DClosestPoint](https://postgis.net/docs/ST_3DClosestPoint.html) | | |
|             |         | st_envelopesintersect | envelopesintersects |
|           |         |        | filtermbrcontains |
|           |         |        | filtermbrintersects |
|           |         |        | filtermbrwithin |
|           |         |        | garsmbr |
|           |         |        | getfacebypoint |
|           |         |        | getfaceedges |
|           |         |        | getfacegeometry |
|           |         |        | getlinkbypoint |
|           |         |        | getnetnodebypoint |
|           |         |        | getnodebypoint |
|           |         |        | mbrcontains |
|           |         |        | mbrdisjoint |
|           |         |        | mbrequal |
|           |         |        | mbrintersects |
|           |         |        | mbroverlaps |
|           |         |        | mbrtouches |
|           |         |        | mbrwithin |
|           |         |        | ptdistwithin |
|           |         |        | relatematch |
|           | st_setsrid | st_setsrid | setsrid |
|           |         |        | sharedpaths |
|           |         |        | validatetopogeo |
|           |         |        | validlogicalnet |
|           |         |        | validspatialnet |
|           | st_dwithin | st_dwithin | |
|           |         | st_lineintersector | |
|           |         | st_orderingequals | |
|           | @ | | |
|           | && | | |
|           | &< | | |
|           | &<\| | | |
|           | &> | | |
|           | << | | |
|           | <<\| | | |
|           | = | | |
|           | >> | | |
|           | \|&> | | |
|           | \|>> | | |
|           | ~ | | |
|           | ~= | | |
|           | st_containsproperly | | |
|           | st_linecrossingdirection | | |
|           | st_orderingequals | | |
|           | st_point_inside_circle | | |

### Measure 
| GeoSPARQL | PostGIS | H2GIS | Spatialite |
|-----------|---------|--------|------------|
| geof:area | st_area | st_area | area |
|           | [CG_3DArea](https://postgis.net/docs/CG_3DArea.html) | [st_3darea](https://h2gis.readthedocs.io/en/latest/ST_3DArea.html) | |
| geof:perimeter | st_perimeter | st_perimeter | perimeter |
|           | st_perimeter2d | | |
|           | [st_perimeter3d](https://postgis.net/docs/ST_3DPerimeter.html) | [st_3dperimeter](https://h2gis.readthedocs.io/en/latest/ST_3DPerimeter.html) | |
| geof:metricPerimeter | | | |
| geof:length | st_length | st_length | length |
|           | [ST_3DLength](https://postgis.net/docs/ST_3DLength.html) | [ST_3DLength](https://h2gis.readthedocs.io/en/latest/ST_3DLength.html) | 3dlength |
| geof:metricArea | | | |
| geof:metricLength | | | |
|           |         |        | geodesic length |
|           |         |        | geodesicarcarea |
|           |         |        | geodesicarcheight |
|           |         |        | geodesicarclength |
|           |         |        | geodesiccentralangle |
|           |         |        | geodesicchordlength |
|           |         |        | great circle length |
|           |         |        | linestringavgsegmentlength |
|           | [st_length_spheroid](https://postgis.net/docs/ST_Length_Spheroid.html) | | |
|           | st_length2d | | |
|           | st_length2d_spheroid | | |
|           | st_length3d_spheroid | | |
|           |         |        | linestringminsegmentlength |
|           |         | [st_svf](https://h2gis.readthedocs.io/en/latest/ST_SVF.html) | |
|           |         | [st_sunposition](https://h2gis.readthedocs.io/en/latest/ST_SunPosition.html) | |
| geof:distance | st_distance | st_distance | distance |
|           | [st_distanceCPA](https://postgis.net/docs/ST_DistanceCPA.html) | | |
| geof:metricDistance | | | |
|           | [ST_3DDistance](https://postgis.net/docs/ST_3DDistance.html) | | 3ddistance |
|           | [CG_Volume](https://postgis.net/docs/CG_Volume.html) | | |
|           | [ST_GeometricMedian](https://postgis.net/docs/ST_GeometricMedian.html) | | |
|           |         |        | abs |
|           |         |        | acos |
|           |         |        | asin |
|           |         |        | atan |
|           |         |        | atan2 |
|           | st_azimuth | st_azimuth | azimuth |
|           |         |        | ceil |
|           |         |        | ceiling |
|           |         |        | centimeter |
|           |         |        | circularity |
|           |         |        | cos |
|           |         |        | cot |
|           |         |        | curvosityindex |
|           |         |        | dd to dms |
|           |         |        | decimeter |
|           |         |        | degrees |
|           |         |        | distancewithin |
|           |         |        | dms to dd |
|           |         |        | downhillheight |
|           |         |        | exp |
|           | st_extent | st_extent | extent |
|           | [ST_3DExtent](https://postgis.net/docs/ST_3DExtent.html) | | |
|           |         |        | floor |
|           |         |        | frechetdistance |
|           |         |        | gcp_compute |
|           |         |        | geosmaximuminscribedcircle |
|           |         |        | geosminimumboundingcenter |
|           |         |        | geosminimumboundingcircle |
|           |         |        | geosminimumboundingradius |
|           |         |        | geosminimumclearance |
|           |         |        | geosminimumclearanceline |
|           |         |        | geosminimumrotatedrectangle |
|           |         |        | geosminimumwidth |
|           |         |        | getlayerextent |
|           |         |        | getvirtualtableextent |
|           | st_hausdorffdistance | | hausdorffdistance |
|           | st_line_locate_point | | line_locate_point |
|           | st_locate_along_measure | | locatealongmeasure |
|           | st_locate_between_measures | | locatebetweenmeasures |
|           | st_maxdistance | st_maxdistance | maxdistance |
|           | [3DMaxDistance](https://postgis.net/docs/ST_3DMaxDistance.html) | | 3dmaxdistance |
|           | st_shortestline | st_shortestline | shortestline |
|           | [st_3dshortestline](https://postgis.net/docs/ST_3DShortestLine.html) | | |
|           |         |        | updownheight |
|           |         |        | uphillheight |
|           |         | st_closestcoordinate | |
|           |         | st_furthestcoordinate | |
|           |         | st_locatealong | |
|           | st_longestline | st_longestline | |
|           | [st_3DLongestLine](https://postgis.net/docs/ST_3DLongestLine.html) | | |
|           | st_distance_sphere | | |
|           | st_distance_spheroid | | |

### Count

| GeoSPARQL | PostGIS | H2GIS | Spatialite |
|-----------|---------|--------|------------|
| geof:numGeometries | [st_numgeometries](https://postgis.net/docs/ST_NumGeometries.html) | st_numgeometries | numgeometries |
| geof:numPoints | st_numpoints | st_numpoints | numpoints |
|           | [st_numpatches](https://postgis.net/docs/ST_NumPatches.html) | | |
| geof:numInteriorRing | | | |
| geof:numPatches | | | |
|           | ST_NumCurves | | |
|           | [st_npoints](https://postgis.net/docs/ST_NPoints.html) | st_npoints | npoints |
|           | [st_nrings](https://postgis.net/docs/ST_NRings.html) | | nrings |
|           | st_numinteriorring | st_numinteriorring | numinteriorring |
|           | st_numinteriorrings | st_numinteriorrings | numinteriorrings |
|           | [st_locatebetweenelevations](https://postgis.net/docs/ST_LocateBetweenElevations.html) | | |

### Properties 

| GeoSPARQL | PostGIS | H2GIS | Spatialite |
|-----------|---------|--------|------------|
|           |         | [st_is3d](https://h2gis.readthedocs.io/en/latest/ST_Is3D.html) | is3d |
| geof:x | [st_x](https://postgis.net/docs/ST_X.html) | st_x | x |
| geof:maxX | [st_xmax](https://postgis.net/docs/ST_XMax.html) | st_xmax | |
| geof:minX | [st_xmin](https://postgis.net/docs/ST_XMin.html) | st_xmin | |
| geof:y | [st_y](https://postgis.net/docs/ST_Y.html) | st_y | y |
| geof:maxY | [st_ymax](https://postgis.net/docs/ST_YMax.html) | st_ymax | |
| geof:minY | [st_ymin](https://postgis.net/docs/ST_YMin.html) | st_ymin | |
| geof:z | [st_z](https://postgis.net/docs/ST_Z.html) | [st_z](https://h2gis.readthedocs.io/en/latest/ST_Z.html) | z |
| geof:maxZ | [st_zmax](https://postgis.net/docs/ST_ZMax.html) | [st_zmax](https://h2gis.readthedocs.io/en/latest/ST_ZMax.html) | maxz |
| geof:minZ | [st_zmin](https://postgis.net/docs/ST_ZMin.html) | [st_zmin](https://h2gis.readthedocs.io/en/latest/ST_ZMin.html) | minz |
| geof:m | [st_m](https://postgis.net/docs/ST_M.html) | [ST_M](https://h2gis.readthedocs.io/en/latest/ST_M.html) | m |
| geof:centroid | st_centroid | st_centroid | centroid |
| geof:geometryN | st_geometryn | st_geometryn | geometryn |
| geof:getSRID | st_srid | st_srid | srid |
| geof:isEmpty | st_isempty | st_isempty | isempty |
| geof:isSimple | [st_issimple](https://postgis.net/docs/ST_IsSimple.html) | st_issimple | issimple |
| geof:endPoint | [st_endpoint](https://postgis.net/docs/ST_EndPoint.html) | st_endpoint | endpoint |
| geof:exteriorRing | [st_exteriorring](https://postgis.net/docs/ST_ExteriorRing.html) | st_exteriorring | exteriorring |
| geof:interiorRingN | [st_interiorringn](https://postgis.net/docs/ST_InteriorRingN.html) | st_interiorringn | interiorringn |
| geof:isRing | st_isring | st_isring | isring |
| geof:pointN | [st_pointn](https://postgis.net/docs/ST_PointN.html) | st_pointn | pointn |
| geof:startPoint | [st_startpoint](https://postgis.net/docs/ST_StartPoint.html) | st_startpoint | startpoint |
| geof:easting | | | |
| geof:northing | | | |
| geof:isClosed | [st_isclosed](https://postgis.net/docs/ST_IsClosed.html) | st_isclosed | isclosed |
|           | [CG_IsPlanar](https://postgis.net/docs/CG_IsPlanar.html) | | |
|           | [CG_IsSolid](https://postgis.net/docs/CG_IsSolid.html) | | |
|           | [ST_IsCollection](https://postgis.net/docs/ST_IsCollection.html) | | |
|           |         |        | atm_determinant |
|           |         |        | atm_isinvertible |
|           |         |        | atm_isvalid |
|           |         |        | bufferoptions_getendcapstyle |
|           |         |        | bufferoptions_getjoinstyle |
|           |         |        | bufferoptions_getmitrelimit |
|           |         |        | bufferoptions_getquadrantsegments |
|           |         |        | checkwithoutrowid |
|           |         |        | checkspatialindex |
|           |         |        | checkspatialmetadata |
|           | [st_coorddim](https://postgis.net/docs/ST_CoordDim.html) | st_coorddim | coorddimension |
|           | st_dimension | st_dimension | dimension |
|           | st_geohash | | geohash |
|           | [Geometrytype](https://postgis.net/docs/GeometryType.html) | | geometrytype |
|           |         |        | getdecimalprecision |
|           |         |        | getgpkgamphibiousmode |
|           |         |        | getgpkgmode |
|           |         |        | getisometadataid |
|           |         |        | getpointindex |
|           |         |        | gpkg_isassignable |
|           |         |        | gpkggetimagetype |
|           |         |        | gpkggetnormalrow |
|           |         |        | gpkggetnormalzoom |
|           |         |        | hasepsg |
|           |         |        | hasfreexl |
|           |         |        | hasgcp |
|           |         |        | hasgeocallbacks |
|           |         |        | hasgeopackage |
|           |         |        | hasgeos |
|           |         |        | hasgeos3100 |
|           |         |        | hasgeos3110 |
|           |         |        | hasgeosadvanced |
|           |         |        | hasgeosonlyreentrant |
|           |         |        | hasgeosreentrant |
|           |         |        | hasgeostrunk |
|           |         |        | hasiconv |
|           |         |        | hasknn |
|           |         |        | haslibxml2 |
|           |         |        | hasmathsql |
|           |         |        | hasminizip |
|           |         |        | hasproj |
|           |         |        | hasproj6 |
|           |         |        | hasrouting |
|           |         |        | hasrttopo |
|           |         |        | hastopology |
|           |         |        | isgeometryblob |
|           |         |        | iscompressedgeometryblob |
|           |         |        | ismeasured |
|           | [ST_IsPolygonCCW](https://postgis.net/docs/ST_IsPolygonCCW.html) | | ispolygonccw |
|           | [ST_IsPolygonCW](https://postgis.net/docs/ST_IsPolygonCW.html) | | ispolygoncw |
|           | st_isvalid | st_isvalid | isvalid |
|           | [st_IsValidTrajectory](https://postgis.net/docs/ST_IsValidTrajectory.html) | | |
|           |         | st_isvaliddetail | isvaliddetail |
|           | st_isvalidreason | st_isvalidreason | isvalidreason |
|           |         |        | isvalidtrajectory |
|           |         |        | maxm |
|           |         |        | mbrmaxx |
|           |         |        | mbrmaxy |
|           |         |        | mbrminx |
|           |         |        | mbrminy |
|           |         |        | minm |
|           | [st_ndims](https://postgis.net/docs/ST_NDims.html) | | ndims |
|           |         |        | selfintersections |
|           |         |        | topogeo_getedgeseed |
|           |         |        | topogeo_getfaceseed |
|           |         |        | topogeo_lineedgeslist |
|           |         |        | topogeo_polyfaceslist |
|           |         |        | toponet_getlinkseed |
|           |         |        | toponet_linelinkslist |
|           |         |        | xb_getabstract |
|           |         |        | xb_getdocument |
|           |         |        | xb_getdocumentsize |
|           |         |        | xb_getencoding |
|           |         |        | xb_getfileid |
|           |         |        | xb_getinternalschemauri |
|           |         | st_compactnessratio | |
|           | st_geometrytype | st_geometrytype | |
|           |         | st_geometrytypecode | |
|           |         | st_holes | |
|           |         | st_isrectangle | |
|           | [box3d](https://postgis.net/docs/Box3D.html) | | |
|           | [st_curveN](https://postgis.net/docs/ST_CurveN.html) | | |
|           | st_estimated_extent | | |
|           | st_extent3d | | |
|           | [st_hasarc](https://postgis.net/docs/ST_HasArc.html) | | |
|           | [st_hasM](https://postgis.net/docs/ST_HasM.html) | | |
|           | [st_hasZ](https://postgis.net/docs/ST_HasZ.html) | | |
|           | st_summary | | |
|           | [st_zmflag](https://postgis.net/docs/ST_Zmflag.html) | | |

### Topography
| GeoSPARQL | PostGIS | H2GIS | Spatialite |
|-----------|---------|--------|------------|
|           |         | [st_drape](https://h2gis.readthedocs.io/en/latest/ST_Drape.html) | |
|           |         | [st_triangleaspect](https://h2gis.readthedocs.io/en/latest/ST_TriangleAspect.html) | |
|           |         | [st_trianglecontouring](https://h2gis.readthedocs.io/en/latest/ST_TriangleContouring.html) | |
|           |         | [st_triangledirection](https://h2gis.readthedocs.io/en/latest/ST_TriangleDirection.html) | |
|           |         | [st_triangleslope](https://h2gis.readthedocs.io/en/latest/ST_TriangleSlope.html) | |
|           |         | [st_voronoi](https://h2gis.readthedocs.io/en/latest/ST_Voronoi.html) | |
|           | [CG_ApproximateMedialAxis](https://postgis.net/docs/CG_ApproximateMedialAxis.html) | | |
|           | [CG_Orientation](https://postgis.net/docs/CG_Orientation.html) | | |
|           | [CG_StraightSkeleton](https://postgis.net/docs/CG_StraightSkeleton.html) | | |
|           | [CG_Visibility](https://postgis.net/docs/CG_Visibility.html) | | |
|           |         |         | geoslargestemptycircle |
|           | [st_mem_size](https://postgis.net/docs/ST_MemSize.html) | | |


### Triangulation
| GeoSPARQL | PostGIS | H2GIS | Spatialite |
|-----------|---------|--------|------------|
|           |         | [st_constraineddelaunay](https://h2gis.readthedocs.io/en/latest/ST_ConstrainedDelaunay.html) | constraineddelaunaytriangulation |
|           | [st_DelaunayTriangles](https://postgis.net/docs/ST_DelaunayTriangles.html) | | |
|           | [CG_ConstrainedDelaunayTriangles](https://postgis.net/docs/CG_ConstrainedDelaunayTriangles.html) | | |
|           |         |         | delaunaytriangulation |
|           |         | [st_delaunay](https://h2gis.readthedocs.io/en/latest/ST_Delaunay.html) | |
|           | [CG_AlphaWrapping](https://postgis.net/docs/CG_AlphaWrapping.html) | | |


### Export / Import
| GeoSPARQL | PostGIS | H2GIS | Spatialite |
|-----------|---------|--------|------------|
|           |         |        | exportdbf |
|           |         |        | exportdxf |
|           |         |        | exportgeojson2 |
|           |         |        | exportkml |
|           |         |        | exportshp |
|           |         |        | importdbf |
|           |         |        | importdxf |
|           |         |        | importdxffromdir |
|           |         |        | importgeojson |
|           |         |        | importshp |
|           |         |        | importwfs |
|           |         |        | importxls |
|           |         |        | importzipdbf |
|           |         |        | importzipshp |
|           |         |        | initfdospatialmetadata |
|           |         |        | initspatialmetadata |
|           |         |        | initspatialmetadatafull |
|           |         |        | insertepsgsrid |
|           |         |        | topogeo_exporttopolayer |
|           |         |        | topogeo_fromgeotable |
|           |         |        | topogeo_fromgeotableext |
|           |         |        | topogeo_fromgeotablenoface |
|           |         |        | topogeo_fromgeotablenofaceext |
|           |         |        | topogeo_togeotable |
|           |         |        | topogeo_togeotablegeneralize |
|           |         |        | toponet_fromgeotable |
|           |         |        | toponet_togeotable |
|           |         |        | toponet_togeotablegeneralize |
|           | find_srid | | |

### Other
| GeoSPARQL | PostGIS | H2GIS | Spatialite |
|---|---|---|---|
|  |  |  | autofdostart |
|  |  |  | autofdostop |
|  |  |  | autogpkgstart |
|  |  |  | autogpkgstop |
|  |  |  | check_strict_sql_quoting |
|  |  |  | checkduplicaterows |
|  |  |  | checkgeopackagemetadata |
|  |  |  | checkshadowedrowid |
|  |  |  | clonetable |
|  |  |  | countunsafetriggers |
|  |  |  | createclonedtable |
|  |  |  | createisometadatatables |
|  |  |  | creatembrcache |
|  |  |  | createmetacatalogtables |
|  |  |  | createmissingrasterlite2columns |
|  |  |  | createmissingsystemtables |
|  |  |  | createrastercoveragestable |
|  |  |  | createrouting |
|  |  |  | createrouting_getlasterror |
|  |  |  | createspatialindex |
|  |  |  | createstylingtables |
|  |  |  | createtemporaryspatialindex |
|  |  |  | createtopotables |
|  |  |  | createuuid |
|  |  |  | createvectorcoveragestables |
|  |  |  | decodeurl |
|  |  |  | dirnamefrompath |
|  |  |  | disablegpkgamphibiousmode |
|  |  |  | disablegpkgmode |
|  |  |  | disablepause |
|  |  |  | disablespatialindex |
|  |  |  | disabletinypoint |
|  |  |  | droptable |
|  |  |  | enablegpkgamphibiousmode |
|  |  |  | enablegpkgmode |
|  |  |  | enablepause |
|  |  |  | enabletinypoint |
|  |  |  | encodeurl |
|  |  |  | eval |
|  |  |  | fileextfrompath |
|  |  |  | filenamefrompath |
|  |  |  | freexl_version |
|  |  |  | fullfilenamefrompat |
|  |  |  | geos_version |
|  |  |  | getcuttermessage |
|  |  |  | getdbobjectscope |
|  |  |  | getlastnetworkexception |
|  |  |  | getlasttopologyexception |
|  |  |  | getmimetype |
|  |  |  | gpkgcreatebasetables |
|  |  |  | gpkgcreatetilestable |
|  |  |  | gpkgcreatetileszoomlevel |
|  |  |  | indian chain |
|  |  |  | indian foot |
|  |  |  | indian yard |
|  |  |  | international chain |
|  |  |  | international fathom |
|  |  |  | international foot |
|  |  |  | international inch |
|  |  |  | international link |
|  |  |  | international nautical mile |
|  |  |  | international statute mile |
|  |  |  | international yard |
|  |  |  | invalidatelayerstatistics |
|  |  |  | isdecimalnumber |
|  |  |  | isexifblob |
|  |  |  | isexifgpsblob |
|  |  |  | isgifblob |
|  |  |  | isinteger |
|  |  |  | isjp2blob |
|  |  |  | isjpegblob |
|  |  |  | islowascii |
|  |  |  | isnumber |
|  |  |  | ispauseenabled |
|  |  |  | ispdfblob |
|  |  |  | ispngblob |
|  |  |  | istiffblob |
|  |  |  | istinypointblob |
|  |  |  | istinypointenabled |
|  |  |  | isvalidgpb |
|  |  |  | iswebpblob |
|  |  |  | iszipblob |
|  |  |  | kilometer |
|  |  |  | libxml2_version |
|  |  |  | ln |
|  |  |  | log |
|  |  |  | log10 |
|  |  |  | log2 |
|  |  |  | makestringlist |
|  |  |  | md5checksum |
|  |  |  | md5totalchecksum |
|  |  |  | millimeter |
|  |  |  | pause |
|  |  |  | pi |
|  |  |  | postgresql_getlasterror |
|  |  |  | postgresql_resetlasterror |
|  |  |  | postgresql_setlasterror |
|  |  |  | pow |
|  |  |  | power |
|  |  |  | proj_getdatabasepath |
|  |  |  | proj_guesssridfromshp |
|  |  |  | proj_guesssridfromwkt |
|  |  |  | proj_guesssridfromzipshp |
|  |  |  | proj_setdatabasepath |
|  |  |  | proj_version |
|  |  |  | radians |
|  |  |  | rebuildgeometrytriggers |
|  |  |  | recoverfdogeometrycolumn |
|  |  |  | recovergeometrycolumn |
|  |  |  | recoverspatialindex |
|  |  |  | recreateisometarefstriggers |
|  |  |  | recreaterastercoveragestriggers |
|  |  |  | recreatestylingtriggers |
|  |  |  | recreatetopotriggers |
|  |  |  | recreatevectorcoveragestriggers |
|  |  |  | registerdatalicense |
|  |  |  | registerisometadata |
|  |  |  | registervirtualgeometry |
|  |  |  | removeduplicaterows |
|  |  |  | removeextraspaces |
|  |  |  | renamecolumn |
|  |  |  | renamedatalicense |
|  |  |  | renametable |
|  |  |  | rl2_mapconfigurationabstractn |
|  |  |  | rl2_mapconfigurationnamen |
|  |  |  | rl2_mapconfigurationtitlen |
|  |  |  | rl2_nummapconfigurations |
|  |  |  | rl2_registermapconfiguration |
|  |  |  | rl2_reloadmapconfiguration |
|  |  |  | rl2_unregistermapconfiguration |
|  |  |  | rttopo_version |
|  |  |  | se_autoregisterstandardbrushes |
|  |  |  | se_registerexternalgraphic |
|  |  |  | se_registerrastercoveragekeyword |
|  |  |  | se_registerrastercoveragesrid |
|  |  |  | se_registerrasterstyle |
|  |  |  | se_registerrasterstyledlayer |
|  |  |  | se_registerspatialviewcoverage |
|  |  |  | se_registertopogeocoverage |
|  |  |  | se_registertoponetcoverage |
|  |  |  | se_registervectorcoverage |
|  |  |  | se_registervectorcoveragekeyword |
|  |  |  | se_registervectorcoveragesrid |
|  |  |  | se_registervectorstyle |
|  |  |  | se_registervectorstyledlayer |
|  |  |  | se_registervirtualtablecoverage |
|  |  |  | se_reloadvectorstyle |
|  |  |  | se_setvectorcoveragecopyright |
|  |  |  | se_setvectorcoverageinfos |
|  |  |  | se_setvectorcoveragevisibilityrange |
|  |  |  | se_unregisterexternalgraphic |
|  |  |  | se_unregisterrastercoveragekeyword |
|  |  |  | se_unregisterrastercoveragesrid |
|  |  |  | se_unregisterrasterstyle |
|  |  |  | se_unregisterrasterstyledlayer |
|  |  |  | se_unregistervectorcoverage |
|  |  |  | se_unregistervectorcoveragekeyword |
|  |  |  | se_unregistervectorcoveragesrid |
|  |  |  | se_unregistervectorstyle |
|  |  |  | se_unregistervectorstyledlayer |
|  |  |  | sequence_currval |
|  |  |  | sequence_lastval |
|  |  |  | sequence_nextval |
|  |  |  | sequence_setval |
|  |  |  | setdatalicenseurl |
|  |  |  | sign |
|  |  |  | sin |
|  |  |  | spatialite_target_cpu |
|  |  |  | spatialite_version |
|  |  |  | sqlproc_allvariables |
|  |  |  | sqlproc_cookedsql |
|  |  |  | sqlproc_execute |
|  |  |  | sqlproc_executeloop |
|  |  |  | sqlproc_fromfile |
|  |  |  | sqlproc_fromtext |
|  |  |  | sqlproc_getlasterror |
|  |  |  | sqlproc_getlogfile |
|  |  |  | sqlproc_isvalid |
|  |  |  | sqlproc_numvariables |
|  |  |  | sqlproc_rawsql |
|  |  |  | sqlproc_return |
|  |  |  | sqlproc_setlogfile |
|  |  |  | sqlproc_variablen |
|  |  |  | sqlproc_varvalue |
|  |  |  | sqrt |
|  |  |  | stddev_pop |
|  |  |  | stddev_samp |
|  |  |  | storedproc_createtables |
|  |  |  | storedproc_delete |
|  |  |  | storedproc_execute |
|  |  |  | storedproc_executeloop |
|  |  |  | storedproc_get |
|  |  |  | storedproc_register |
|  |  |  | storedvar_delete |
|  |  |  | storedvar_get |
|  |  |  | storedvar_getvalue |
|  |  |  | storedvar_register |
|  |  |  | tan |
|  |  |  | u.s. chain |
|  |  |  | u.s. foot |
|  |  |  | u.s. inch |
|  |  |  | u.s. statute mile |
|  |  |  | u.s. yard |
|  |  |  | unregisterdatalicense |
|  |  |  | upgradegeometrytriggers |
|  |  |  | var_pop |
|  |  |  | var_samp |
|  |  |  | wms_createtables |
|  |  |  | wms_defaultrefsys |
|  |  |  | wms_defaultsetting |
|  |  |  | wms_getfeatureinforequesturl |
|  |  |  | wms_getmaprequesturl |
|  |  |  | wms_registergetcapabilities |
|  |  |  | wms_registergetmap |
|  |  |  | wms_registerrefsys |
|  |  |  | wms_registersetting |
|  |  |  | wms_registerstyle |
|  |  |  | wms_setgetcapabilitiesinfos |
|  |  |  | wms_setgetmapcopyright |
|  |  |  | wms_setgetmapinfos |
|  |  |  | wms_setgetmapoptions |
|  |  |  | wms_unregistergetcapabilities |
|  |  |  | wms_unregistergetmap |
|  |  |  | wms_unregisterrefsys |
|  |  |  | wms_unregistersetting |
|  |  |  | xb_cacheflush |
|  |  |  | xb_compress |
|  |  |  | xb_create |
|  |  |  | xb_getlastparseerror |
|  |  |  | xb_getlastvalidateerror |
|  |  |  | xb_getlastxpatherror |
|  |  |  | xb_getparentid |
|  |  |  | xb_getpayload |
|  |  |  | xb_getschemauri |
|  |  |  | xb_gettitle |
|  |  |  | xb_iscompressed |
|  |  |  | xb_isgpx |
|  |  |  | xb_isisometadata |
|  |  |  | xb_ismapconfig |
|  |  |  | xb_isschemavalidated |
|  |  |  | xb_issldsevectorstyle |
|  |  |  | xb_issldstyle |
|  |  |  | xb_issvg |
|  |  |  | xb_isvalid |
|  |  |  | xb_isvalidxpathexpression |
|  |  |  | xb_loadxml |
|  |  |  | xb_mlinefromgpx |
|  |  |  | xb_schemavalidate |
|  |  |  | xb_setfileid |
|  |  |  | xb_setparentid |
|  |  |  | xb_storexml |
|  |  |  | xb_uncompress |
|  |  |  | zipfile_dbfn |
|  |  |  | zipfile_numdbf |
|  |  |  | zipfile_numshp |
|  |  |  | zipfile_shpn |
|  | st_accum | st_accum |
|  |  | st_googlemaplink |
|  |  | st_osmmaplink |