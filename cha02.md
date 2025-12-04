# Bijlage 1: 3D Functies en topologie in standaarden

<mark> Functies die gelimiteerd is naar 2 coordinaten en daarbij naar maximaal 2 ruimtelijke dimensies geven we een bepaalde kleur </mark>

OGC Simple Feature Access (SFA):
SQL-POSTGIS Functies

ST_3DIntersects(geomA, geomB) etc. Returns TRUE if the Geometries "spatially intersect" in 3D - only for points, linestrings, polygons, polyhedral surface (area). This method implements the SQL/MM specification. SQL-MM 3: ?


ST_3DDWithin
ST_DWithin

[Topological Relationships and Their Use](https://pure.tudelft.nl/ws/files/9022748/TopologicalRelationshipsTheirUse.pdf)
[infraspatialOT](https://linkedbuildingdata.net/ldac2024/files/papers/LDAC2024_Camera_7.pdf)
[Relative Location Ontology](https://linkedbuildingdata.net/ldac2024/files/papers/LDAC2024_Camera_9.pdf)
http://vigir.missouri.edu/~gdesouza/Research/Conference_CDs/IEEE_CyberIntSys_2008/PDFFILES/Papers/P1139.pdf
[GeoPose](https://docs.ogc.org/is/21-056r11/21-056r11.html)


## Software: 

<table>
<caption></caption>
<thead>
<tr><th colspan = "4">PostGIS</th></tr>
</thead>
<tbody>
<tr>
    <td> <a href "http://www.opengis.net/def/geometry/ISO-19107/2003/GM_Point"> GM_Point</td>
    <td></td>
    <td></td>
    <td></td>
</tr>
</tbody>
</table>

<table>
<caption></caption>
<thead>
<tr><th colspan = "4">GML (3.2.1.)</th></tr>
</thead>
<tbody>
<tr>
    <td> <a href "https://schemas.opengis.net/gml/3.2.1/geometryBasic0d1d.xsd"> gml:Point</td>
    <td></td>
    <td></td>
    <td></td>
</tr>
<tr>
    <td><a href "https://schemas.opengis.net/gml/3.2.1/geometryBasic0d1d.xsd">gml:LineString</td>
    <td><a href "https://schemas.opengis.net/gml/3.2.1/geometryBasic0d1d.xsd">gml:Curve</td>
    <td><a href "https://schemas.opengis.net/gml/3.2.1/geometryPrimitives.xsd">gml:OrientableCurve</td>
    <td><a href "https://schemas.opengis.net/gml/3.2.1/geometryComplexes.xsd">gml:CompositeCurve</td>
</tr>

<tr>
    <td><a href "https://schemas.opengis.net/gml/3.2.1/geometryBasic2d.xsd">gml:Polygon</td>
    <td><a href "https://schemas.opengis.net/gml/3.2.1/geometryBasic2d.xsd">gml:LinearRing</td>
    <td><a href "https://schemas.opengis.net/gml/3.2.1/geometryPrimitives.xsd"> gml:Ring</td>
    <td><a href "https://schemas.opengis.net/gml/3.2.1/geometryPrimitives.xsd"> gml:Circle</td>
    <td><a href "https://schemas.opengis.net/gml/3.2.1/geometryPrimitives.xsd"> gml:CircleByCenterPoint</td>
</tr>
<tr>
    <td><a href "https://schemas.opengis.net/gml/3.2.1/geometryPrimitives.xsd">gml:BSpline</td>
    <td><a href "https://schemas.opengis.net/gml/3.2.1/geometryPrimitives.xsd">gml:Bezier</td>
    <td><a href "https://schemas.opengis.net/gml/3.2.1/geometryPrimitives.xsd">gml:Knot</td>
    <td></td>
</tr>
<tr>
    <td><a href "https://schemas.opengis.net/gml/3.2.1/geometryPrimitives.xsd"> gml:Arc</td>
    <td><a href "https://schemas.opengis.net/gml/3.2.1/geometryPrimitives.xsd">gml:ArcByBulge</td>
    <td><a href "https://schemas.opengis.net/gml/3.2.1/geometryPrimitives.xsd">gml:ArcString</td>
    <td><a href "https://schemas.opengis.net/gml/3.2.1/geometryPrimitives.xsd"> gml:ArcStringByBulge</td>
    <td><a href "https://schemas.opengis.net/gml/3.2.1/geometryPrimitives.xsd"> gml:CubicSpline</td>

</tr>
<tr>
    <td><a href "https://schemas.opengis.net/gml/3.2.1/geometryPrimitives.xsd">gml:Surface</td>
    <td><a href "https://schemas.opengis.net/gml/3.2.1/geometryPrimitives.xsd">gml:PolyhedralSurface</td>
    <td><a href "https://schemas.opengis.net/gml/3.2.1/geometryPrimitives.xsd">gml:TriangulatedSurface</td>
    <td><a href "https://schemas.opengis.net/gml/3.2.1/geometryPrimitives.xsd">gml:Tin</td>
    <td><a href "https://schemas.opengis.net/gml/3.2.1/geometryPrimitives.xsd">gml:OrientableSurface</td>
    <td><a href "https://schemas.opengis.net/gml/3.2.1/geometryComplexes.xsd">gml:CompositeSurface</td>
</tr>
<tr>
    <td><a href "https://schemas.opengis.net/gml/3.2.1/geometryPrimitives.xsd">gml:PolygonPatch</td>
    <td><a href "https://schemas.opengis.net/gml/3.2.1/geometryPrimitives.xsd">gml:Triangle</td>
    <td><a href "https://schemas.opengis.net/gml/3.2.1/geometryPrimitives.xsd">gml:Rectangle</td>
    <td><a href "https://schemas.opengis.net/gml/3.2.1/geometryPrimitives.xsd">gml:PointGrid</td>
    <td></td>
</tr>
<tr>
    <td><a href "https://schemas.opengis.net/gml/3.2.1/geometryPrimitives.xsd">gml:Cone</td>
    <td><a href "https://schemas.opengis.net/gml/3.2.1/geometryPrimitives.xsd">gml:Cylinder</td>
    <td><a href "https://schemas.opengis.net/gml/3.2.1/geometryPrimitives.xsd">gml:Sphere</td>
    <td></td>
</tr>
<tr>
    <td><a href "https://schemas.opengis.net/gml/3.2.1/geometryPrimitives.xsd">gml:Solid</td>
    <td><a href "https://schemas.opengis.net/gml/3.2.1/geometryPrimitives.xsd">gml:Shell</td>
    <td><a href "https://schemas.opengis.net/gml/3.2.1/geometryPrimitives.xsd">gml:CompositeSolid</td>
    <td></td>
    <td></td>
</tr>
<tr>
    <td><a href "https://schemas.opengis.net/gml/3.2.1/geometryAggregates.xsd">gml:MultiPoint</td>
    <td><a href "https://schemas.opengis.net/gml/3.2.1/geometryAggregates.xsd">gml:MultiCurve</td>
    <td><a href "https://schemas.opengis.net/gml/3.2.1/geometryAggregates.xsd">gml:MultiSurface</td>
    <td><a href "https://schemas.opengis.net/gml/3.2.1/geometryAggregates.xsd">gml:MultiSolid</td>
</tr>

<tr>
    <td><a href "https://schemas.opengis.net/gml/3.2.1/coverage.xsd">gml:RectifiedGridCoverage</td>
    <td><a href "https://schemas.opengis.net/gml/3.2.1/geometryAggregates.xsd">gml:GridCoverage</td>
    <td></td>
    <td></td>
</tr>
</tbody>
</table>


GM_Solid gml:Solid gml:SolidType gml:SolidPropertyType
 gml:OrientableCurve gml:OrientableCurveType gml:CurvePropertyType
 gml:OrientableSurface gml:OrientableSurfaceType gml:SurfacePropertyType
 gml:Ring gml:RingType —
gml:Shell gml:ShellType —
— gml:LineString gml:LineStringType —
— gml:Polygon gml:PolygonType —
— gml:LinearRing gml:LinearRingType —
 gml:Point gml:PointType gml:PointPropertyType
 gml:CompositeCurve gml:CompositeCurveType anonymous property type
 gml:CompositeSurface gml:CompositeSurfaceType anonymous property type
 gml:CompositeSolid gml:CompositeSolidType anonymous property type
GM_Complex gml:GeometricComplex gml:GeometricComplexType gml:GeometricComplexPropertyType
GM_Aggregate gml:MultiGeometry gml:MultiGeometryType gml:MultiGeometryPropertyType
 gml:MultiPoint gml:MultiPointType gml:MultiPointPropertyType
 gml:MultiCurve gml:MultiCurveType gml:MultiCurvePropertyType
 gml:MultiSurface gml:MultiSurfaceType gml:MultiSurfacePropertyType
 gml:MultiSolid gml:MultiSolidType gml:MultiSolidPropertyType
GM_MultiPrimitive gml:MultiGeometry gml:MultiGeometryType gml:MultiGeometryPropertyType
GM_CurveSegment gml:AbstractCurveSegment gml:AbstractCurveSegmentType —
 gml:ArcType —
 gml:ArcByBulge gml:ArcByBulgeType —
— gml:ArcByCenterPoint gml:ArcByCenterPointType —
  gml:ArcStringType —
  gml:ArcStringByBulgeType —
 gml:BezierType —
  gml:BSplineType —



<table>
<caption></caption>
<thead>
<tr><th colspan = "4">WKT</th></tr>
</thead>
<tbody>
<tr><td style="background-color: #FFF0F5"> POINT<small>(x y)</small></td><td>POINT Z<small>(x y z)</small></td><td style="background-color: #FFF0F5">POINT M<small>(x y m)</small></td><td>POINT ZM<small>(x y z m)</small></td></tr>
<tr><td style="background-color: #FFF0F5"> LINESTRING<small>(x y, x y)</small></td><td>LINESTRING Z<small>(x y z, x y z)</small></td><td style="background-color: #FFF0F5">LINESTRING M<small>(x y m, x y m)</small></td><td>LINESTRING ZM<small>(x y z m, x y z m)</small></td></tr>
<tr><td style="background-color: #FFF0F5"> POLYGON<small>(x y, x y, x y)</small></td><td>POLYGON Z<small>(x y z, x y z, x y z)</small></td><td style="background-color: #FFF0F5">POLYGON M<small>(x y m, x y m, x y m)</small></td><td>POLYGON ZM<small>(x y z m)</small></td></tr>
<tr><td style="background-color: #FFF0F5"> POLYHEDRALSURFACE<small>(x y)</small></td><td>POLYHEDRALSURFACE Z<small>(x y z)</small></td><td style="background-color: #FFF0F5">POLYHEDRALSURFACE M<small>(x y m)</small></td><td>POLYHEDRALSURFACE ZM<small>(x y z m)</td></tr>
<tr><td style="background-color: #FFF0F5"> TRIANGLE<small>(x y, x y, x y)</td><td>TRIANGLE Z<small>(x y z, x y z, x y z)</td><td style="background-color: #FFF0F5">TRIANGLE M<small>(x y m, x y m, x y m)</td><td>TRIANGLE ZM<small>(x y z m, x y z m, x y z m)</td></tr>
<tr><td style="background-color: #FFF0F5"> TIN(<small>(x y, x y, x y),(x y, x y, x y))</td><td>TIN Z(<small>(x y z, x y z, x y z),(x y z, x y z, x y z)))</small></td><td style="background-color: #FFF0F5">TIN M(<small>(x y m, x y m, x y m),(x y m, x y m, x y m))</small></td><td>TIN ZM(<small>(x y z m, x y z m, x y z m),(x y z m, x y z m, x y z m))</small></td></tr>
<tr><td style="background-color: #FFF0F5"> MULTIPOINT<small>((x y), (x y))</small></td><td>MULTIPOINT Z<small>((x y z), (x y z))</small></td><td style="background-color: #FFF0F5">MULTIPOINT M<small>((x y m), (x y m))</small></td><td>MULTIPOINT ZM<small>((x y z m),(x y z m))</small></td></tr>
<tr><td style="background-color: #FFF0F5"> MULTILINESTRING<small>((x y, x y), (x y, x y))</small></td><td>MULTILINESTRING Z<small>((x y z, x y z), (x y z, x y z))</small></td><td style="background-color: #FFF0F5">MULTILINESTRING M<small>((x y m, x y m), (x y m, x y m))</small></td><td>MULTILINESTRING ZM<small>((x y z m, x y z m),(x y z m, x y z m))</small></td></tr>
<tr><td style="background-color: #FFF0F5"> MULTIPOLYGON<small>((x y, x y, x y),(x y, x y, x y))</small></td><td>MULTIPOLYGON Z<small>((x y z, x y, x y z),(x y z, x y z, x y z))</small></td><td style="background-color: #FFF0F5">MULTIPOLYGON M<small>((x y m, x y m, x y m),(x y m, x y m, x y m))</small></td><td>MULTIPOLYGON ZM<small>((x y z m, x y z m, x y z m),(x y z m, x y z m, x y z m))</small></td></tr>
</tbody>
</table>
</table>

EWKT:
<table>
<caption></caption>
<thead>
<tr><th colspan = "4">WKT</th></tr>
</thead>
<tbody>
<tr><td> <a href "https://dp.schemas.opengis.net/05-029r4/gml/3.2.1/profiles/point/0.4.0/gml311PointProfile.xsd"> gml:Point</td><td>B</td><td>C</td></tr>
<tr><td>D</td><td>E</td><td>F</td></tr>
</tbody>
</table>
</table>

3D Tiles en I3S: 

<table>
<caption></caption>
<thead>
<tr><th colspan = "4">IFC (4x3)</th></tr>
</thead>
<tbody>
<tr><th colspan = "4"><small>Points</small></th></tr>
<tr>
    <td> <a href "https://standards.buildingsmart.org/IFC/RELEASE/IFC4_3/HTML/lexical/IfcCartesianPoint.htm"> IfcCartesianPoint</td>
    <td><a href "https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcPointByDistanceExpression.htm"> IfcPointByDistanceExpression</td>
    <td><a href "https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcPointOnCurve.htm">IfcPointOnCurve</td>
    <td><a href "https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcPointOnSurface.htm">IfcPointOnSurface </td>
</tr>
<tr><td>D</td><td>E</td><td>F</td></tr>
</tbody>
</table>
</table>

<table>
<caption></caption>
<thead>
<tr><th colspan = "4">Open Cascade</th></tr>
</thead>
<tbody>
<tr><th colspan = "4"><small>Points</small></th></tr>
<tr>
    <td> <a href "https://dev.opencascade.org/doc/refman/html/class_geom2d___cartesian_point.html"> Geom2d_CartesianPoint</td>
    <td> <a href "https://dev.opencascade.org/doc/refman/html/class_geom___cartesian_point.html"> Geom_CartesianPoint</td>
    <td> <a href "https://dev.opencascade.org/doc/refman/html/class_geom2d___point.html"> Geom2d_Point</td>
    <td> <a href "https://dev.opencascade.org/doc/refman/html/class_geom___point.html"> Geom_Point</td>
</tr>
<tr><td>D</td><td>E</td><td>F</td></tr>
</tbody>
</table>
</table>


<table>
<caption></caption>
<thead>
<tr><th colspan = "4">STEP</th></tr>
</thead>
<tbody>
<tr><th colspan = "4"><small>Points</small></th></tr>
<tr>
    <td> <a href "https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.cartesian_point"> cartesian_point</td>
    <td>  <a href "https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.cylindrical_point"> cylindrical_point</td>
    <td><a href "https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.spherical_point">spherical_point</td>
    <td><a href "https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.polar_point">polar_point</td>
</tr>
<tr>
    <td><a href "https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.point_on_curve">point_on_curve</td>
    <td><a href "https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.point_on_surface">point_on_surface</td>
    <td><a href"https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.point_in_volume">point_in_volume</td>
    <td><a href"https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.point_replica">point_replica</td>
</tr>
<tr>
    <td><a href"https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.degenerate_pcurve">degenerate_pcurve</td>
    <td><a href"https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.evaluated_degenerate_pcurve">evaluated_degenerate_pcurve</td>
    <td></td>
    <td></td>
</tr>
<tr><th colspan = "4"><small>Lines</small></th></tr>
<tr>
    <td>A</td>
    <td>B</td>
    <td>C</td>
    <td>D</td>
</tr>
</tbody>
</table>

LAZ: 

3D Geovolumes API:



Lines and Curves:
|===
| ISO 19107 | GML | IFC | STEP | OpenCascade | WKT 
||  |  |  | |
|| |  |  | |CIRCULARSTRING(x1 y1, ...)
||  |  | |POLYGON()
|GM_Polygon|   |  | |
| GM_Ring| gml:Ring|  |  |  |
| | gml:Patches|  |  ||

|| IfcBSplineCurveWithKnots  | B_spline_curve_with_knots |Geom2d_BSplineCurve +
Geom_BSplineCurve|
|| | IfcRationalBSplineCurveWithKnots  | ||
||  | bezier_curve |Geom2D_BezierCurve +
Geom_BezierCurve |
|| |  | rational_b_spline_curve ||
|| |  | local_b_spline ||
|| |  | uniform_curve ||
|| |  | quasi_uniform_curve ||
|| |  | locally_refined_spline_curve  ||
|| |  | rational_locally_refined_spline_curve  ||
|| |  | trimmed_curve   |Geom2d_TrimmedCurve +
Geom_TrimmedCurve|
|GM_CompositeCurve| gml:CompositeCurve | IfcCompositeCurve  | ||COMPOUNDCURVE(...)
|| | IfcCompositeCurveOnSurface  | ||
|| | IfcBoundaryCurve | boundary_curve||
|| | IfcOuterBoundaryCurve|outer_boundary_curve ||
|| | IfcGradientCurve  | ||
|| | IfcSegmentedReferenceCurve  | ||
|| | IfcIndexedPolyCurve  | ||
|GM_LineString | gml:LineStringSegment | | ||LINESTRING(x1 y1, x2 y2, ...)
|| | IfcPolyline  | polyline |TopoDS_Wire|
|| | IfcTrimmedCurve  | ||
||| IfcCircle |circle |Geom2d_Circle +
Geom_Circle|
|| | IfcElipse | elipse |Geom2d_Ellipse +
Geom_Ellipse|
|| | IfcLine  | line |Geom2d_Line +
Geom_Line|
|| |  | hyperbola |Geom2d_Hyperbola +
Geom_Hyperbola|
|| |  | parabola |Geom2d_Parabola +
Geom_Parabola|
|| gml:OffsetCurve | IfcOffsetCurve2D | offset_curve_2d |Geom2d_OffsetCurve +
Geom_OffsetCurve|
|| | IfcOffsetCurve3D | offset_curve_3d ||
|| | IfcOffsetCurveByDistances | ||
|| | IfcPcurve | pcurve  ||
|| |  | bounded_pcurve  ||
|| | IfcPolynomialCurve | ||
|| | IfcClothoid |clothoid ||
|| |  |circular_involute ||
|| | IfcCosineSpiral | ||
|| | IfcSecondOrderPolynomialSpiral | ||
|| | IfcThirdOrderPolynomialSpiral | ||
|| | IfcSeventhOrderPolynomialSpiral | ||
|| | IfcSineSpiral | ||
|| | IfcSurfaceCurve | surface_curve ||
|| |  | intersection_curve ||
|| |  | seam_curve ||
|| |  | bounded_surface_curve ||
|| |  | composite_curve_on_surface ||
|| |  | curve_replica ||
|| | IfcSeamCurve| ||
|| | |Geom2d_VectorWithMagnitude +
Geom_VectorWithMagnitude  ||
|===

Composites:
|===
| ISO 19107 | GML | IFC | STEP | OpenCascade | WKT 
|| | | composite_curve||
|| | | composite_curve_segment ||
|| | | reparametrised_composite_curve_segment ||
|===

Surface:
|===
| ISO 19107 | GML | IFC | STEP | OpenCascade | WKT | X3D
|GM_SurfacePatch | |  |  |||
|GM_PointGrid|   |  |||
|GM_ParametricCurveSurface| |  |  |||
|GM_GriddedSurface| |  |  |||
|| | |plane |Geom_Plane ||
|| | |cylindrical_surface |Geom_CylindricalSurface||
|| | |conical_surface |Geom_ConicalSurface||
|| | |spherical_surface |Geom_SphericalSurface||
|| | |toroidal_surface |Geom_ToroidalSurface||
|| | |degenerate_toroidal_surface|||
|| | |dupin_cyclide_surface |||
|| | |surface_of_linear_extrusion |Geom_SurfaceOfLinearExtrusion||
|| | |surface_of_revolution |Geom_SurfaceOfRevolution||
|| | |surface_curve_swept_surface |||
|| | |fixed_reference_swept_surface  |||
|| | |b_spline_surface  |Geom_BSplineSurface||
|| | |b_spline_surface_with_knots  |||
|| | |uniform_surface |||
|| | |uasi_uniform_surface |||
|| | |bezier_surface   |Geom_BezierSurface||
|| | |rational_b_spline_surface  |||
|| | |locally_refined_spline_surface   |||
|| | |rational_locally_refined_spline_surface  |||
|| | |curve_bounded_surface  |||
|| | |rectangular_composite_surface  |||
|| | |surface_patch |||
|| | |offset_surface |Geom_OffsetSurface||
|| | |oriented_surface |||
|| | |surface_replica|||
|| | ||Geom_Surface||
|| |  |Geom_OsculatingSurface |||
|| |  |Geom_RectangularTrimmedSurface|||
|===

Primitives:
|===
| ISO 19107 | GML | IFC | STEP | OpenCascade | WKT | X3D
| |  | IfcBlock |block_volume| TopoDS_Solid (BRepPrimAPI_MakeBox) ||Box
||  | IfcRectangularPyramid |pyramid_volume  |||
|GM_Cone| gml:Cone| IfcRightCircularCone| TopoDS_Solid (BRepPrimAPI_MakeCone)  |||Cone
|GM_Cylinder| gml:Cylinder| IfcRightCircularCylinder | cylindrical_volume| TopoDS_Solid (BRepPrimAPI_MakeCylinder) ||Cylinder
|| |  | | TopoDS_Solid (BRepPrimAPI_MakeHalfSpace) ||
|| |  | | TopoDS_Solid (BRepPrimAPI_MakeOneAxis) ||
|| |  | | TopoDS_Solid (BRepPrimAPI_MakePrism) ||
|| |  | | TopoDS_Solid (BRepPrimAPI_MakeRevol) ||
|| |  | | TopoDS_Solid (BRepPrimAPI_MakeRevolution) |||
|GM_Sphere| gml:Sphere| IfcSphere | spherical_volume | TopoDS_Solid (BRepPrimAPI_MakeSphere) ||
|| |  | | TopoDS_Solid (BRepPrimAPI_MakeTorus) ||
|| |  |wedge_volume | TopoDS_Solid (BRepPrimAPI_MakeWedge) ||
|| |  |tetrahedron_volume |  ||
|| |  |cylindrical_volume |  ||
|| |  |eccentric_conical_volume |  ||
|| |  |toroidal_volume |  ||
|| |  |ellipsoid_volume |  ||
|===

Solid:
|===
| ISO 19107 | GML | IFC | STEP | OpenCascade | WKT | X3D
|| gml:AbstractSolid |  |  | ||
|GM_Solid|  |IfcFacetedBrep | manifold_solid_brep  | TopoDS_Solid(TopoDS_Face)||IndexedFaceSet
|| | IfcCsgSolid |Csg_solid |TopoDS_Solid||
|| | IfcAdvancedBrep | |||
|GM_Shell| gml:Shell |  |  | ||
|| |  |b_spline_volume|  ||
|| |  |b_spline_volume_with_knots |  ||
|| |  |bezier_volume |  ||
|| |  |uniform_volume |  ||
|| |  |quasi_uniform_volume   |  ||
|| |  |rational_b_spline_volume  |  ||
|| |  |locally_refined_spline_volume  |  ||
|| |  |rational_locally_refined_spline_volume  |  ||
|===


Boolean Operators:
|===
| ISO 19107 | GML | IFC | OpenCascade | WKT | X3D
||  | IfcBooleanResult(.INTERSECTION) |boolean_operator(intersection) | BRepAlgoAPI_Common||
||  | IfcBooleanResult(.DIFFERENCE) |boolean_operator(difference)  | BRepAlgoAPI_Cut ||
||  | IfcBooleanResult(.UNION) |boolean_operator(union)  | BRepAlgoAPI_Fuse||
||  |  |  | BRepAlgoAPI_Section||
|===

Axis: 
|===
| ISO 19107 | GML | IFC | STEP | OpenCascade | WKT 
|| |  ||Geom2d_AxisPlacement + 
Geom_AxisPlacement||
|| | axis1_placement  |Geom_Axis1Placement||
|| | axis2_placement_2d + 
axis2_placement_3d |Geom_Axis2Placement||
|===




Operators:
|===
| ISO 19107 | GML | IFC | STEP | OpenCascade | WKT 
|| |  |cartesian_transformation_operator||
|| |IfcCartesianTransformationOperator3D|cartesian_transformation_operator_3d ||
|| |IfcCartesianTransformationOperator2D +
IfcCartesianTransformationOperator2DnonUniform|cartesian_transformation_operator_2d||
|===


|===
| ISO 19107 | GML      | STEP | IFC | OpenCascade | WKT 
|| | IfcCartesianPointList2D  | ||
|| | IfcCartesianPointList3D  | ||
|===

Interface Query3D:
|===
| ISO 19107 | GML | IFC | OpenCascade | WKT |
|3Dboundary:Geometry|  |  |  | |
|3DconvexHull:Geometry|  |  |  | |
|3Ddistance|  |  |  | |
|3Dbuffer|  |  |  | |
|3Dintersection|  |  |  | |
|3Ddifference|  |  |  | |
|3DsymDifference|  |  |  | |
|3Dunion|  |  |  | |
|3Dcontains|   |  |  | |
|3Dcrosses  |  |  | ||
|3Ddisjoint  |  |  | ||
|3Dequals|  |  |  | |
|3Dintersects|  |  |  | |
|3Doverlaps |  |  | ||
|3Dtouches|  |  | ||
|3Dwithin|  |  | ||
|3DwithinDistance|  |  | ||
|3Drelate|  |  | ||
|===

https://dev.opencascade.org/doc/refman/html/
https://old.opencascade.com/doc/occt-7.5.0/overview/html/index.html
https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcGeometricRepresentationItem.htm
https://steptools.com/stds/smrl/data/modules/basic_geometry/sys/4_info_reqs.htm
https://www.web3d.org/documents/specifications/19775-1/V4.0/index.html

# Annex B: Allignment of Topology


X3D 
BOX

IFC 
IfcCsgSolid

IfcAdvancedBrep