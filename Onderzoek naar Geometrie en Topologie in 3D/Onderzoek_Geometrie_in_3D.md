# Verschillende geometrie benaderingen

## Boundary Representation
De Boundary Representation methode beschrijft een 3D-volume door de geometrie die het 3D volume begrenst. Dit komt sterk overeen met de manier waarop de Geo-standaarden voor geometrie ook werken. De IFC-geometrie waarmee men een 3D-boundary representation kan maken kent geometrie-typen die in de Geo-standaarden niet ondersteund worden. 

<figure id="Advanced_Brep">
      <img src="../media/Advanced BRep in IFC.png" alt="Advanced_Brep>
      <figcaption>
        <a class="self-link" href="#fig-Advanced_Brep"></bdi></a>
        <span class="fig-title">
        Advanced BRep in IFC gebruik makend van NURBS-curves voor de definitie van de boundary surfaces. <br> 
        bron:
        <a href="https://ifc43-docs.standards.buildingsmart.org/" target="_blank">Building Smart International</a>
        </span>
      </figcaption>
</figure>

## Constructieve Solid Geometrie
Daarnaast kent IFC de methode om op basis van 3D-primitieven en boolean operations tot de juiste 3D-vorm te komen. IFC 4x3 kent onderstaande primitieven:

<figure id="3DPrimitives">
      <img src="../media/Ifc3DPrimitives.png" alt="3DPrimitives">
      <figcaption>
        <a class="self-link" href="#fig-3DPrimitives"></bdi></a>
        <span class="fig-title">
        3D Primities in IFC <br> 
        bron:
        <a href="https://ifc43-docs.standards.buildingsmart.org/" target="_blank">Building Smart International</a>
        </span>
      </figcaption>
</figure>

Deze primitieven kan men samenvoegen, de overlappende delen behouden of de verschillen behouden. 3D primitieven met Union, Intersection en Difference kunnen resulteren in complexe geometrie die met een Boundary representation methode veel meer data kost om dezelfde vormen te beschrijven.

<figure id="CSG">
      <img src="../media/Constructive Solid Geometry.png" alt="CSG">
      <figcaption>
        <a class="self-link" href="#fig-CSG"></bdi></a>
        <span class="fig-title">
        Constructive Solid Geometry met 3D primitieven en Boolean Operators <br> 
        bron:
        <a href="https://mit-crpg.github.io/OpenMOC/methods/constructive_solid_geometry.html" target="_blank">Massachusetts Institute of Technology, 2019</a>
        </span>
      </figcaption>
</figure>

## Constructieve Solid Geometrie
Tenslotte kent IFC een Sweep Volume om 3D geometrie te duiden. Met deze methodiek definieert men een vlak die men over een bepaald pad kan extruderen.

<figure id="Sweep_volume">
      <img src="../media/sweep volumes.png" alt="Sweep_volume">
      <figcaption>
        <a class="self-link" href="#fig-Sweep_volume"></bdi></a>
        <span class="fig-title">
        Sweep volumes <br> 
        bron:
        <a href="https://ifc43-docs.standards.buildingsmart.org/" target="_blank">Building Smart International</a>
        </span>
      </figcaption>
</figure>

Omdat er zoveel verschillende manieren van het definieren van 3D geometrie in IFC zijn zijn er weinig applicaties en viewers die met al deze geometrieën om kunnen gaan. Het is mogelijk om de diversiteit van geometrie te reduceren door geometrie om te rekenen. 

Als een IFC-bestand impliciete geometrie bevat, en conversie gewenst is. Dient impliciete geometrie, expliciet gemaakt te worden door benadering. Geometrie kan men omrekenen naar meshes en boundary representation (Brep). Deze benaderingen komen vaak redelijk dicht bij het originele model, maar er zijn verschillen. Meestal zijn de ruimtelijke verschillen klein en verwaarloosbaar voor de meeste GIS-toepassingen.


<figure id="Mesh_van_Geometrie">
      <img src="../media/Mesh_van_Geometrie.png" alt="Mesh_van_Geometrie">
      <figcaption>
        <a class="self-link" href="#fig-Mesh_van_Geometrie"></bdi></a>
        <span class="fig-title">
        Mesh van een sphere op verschillend detailniveau en verschillende basis-vormen
        </span>
      </figcaption>
</figure>

Het is mogelijk om in OpenBIM, IFC, een subset van geometrie af te dwingen. Hiervoor kan men gebruik maken van een [Model View Definition](https://openbim-knowledgebase.org/en/docs/bimcert-manual-2024/chapter-3-in-depth-knowledge/chapter-3-3-model-view-definition-mvd/). Zie de Reference View in de [MVD-database](https://technical.buildingsmart.org/standards/ifc/mvd/mvd-database/). IFC's die worden geleverd en zich houden aan deze model view definition kunnen daardoor door meer viewers en software ingelezen worden. Het is aan software om deze output te leveren.
Men heeft hierbij geen grip op de instellingen en kwaliteit van de output. Dit is aan de software. 

Wanneer dit wel van belang is kan aparte tooling als [ifcBuildingEnvExtrator](https://github.com/tudelft3d/IFC_BuildingEnvExtractor) ingezet worden. Bij deze tooling heeft men grip op de instellingen van conversie. 

Naast eisen voor kwaliteit van geometrie zullen er eisen zijn aan de entiteiten uit BIM die niet meegenomen moeten worden als een lager detailniveau gewenst is. Bijvoorbeeld een antenne of een deurklink kan buiten beschouwing gelaten worden wanneer een BIM-model naar een lager detailniveau gebracht dient te worden. 

<aside class="note" title="Stel inwinningsregels voor IFC op">
  <p><strong>AANBEVELING:</strong> Stel inwinningsregels voor IFC-conversie op. Dit kan met een IFC Model View Definition Reference View en/of met convertors als IfcBuildingEnvExtractor of IFCConvert geleverd worden.</p>
</aside>

Door het veranderen van het model en de impliciete geometrie naar expliciete geometrie verandert het bestandformaat. BIM-modellen met veel impliciete geometrie kunnen behoorlijk groter worden als daar expliciete geometrie van gemaakt wordt. Het tabel_chairs model is 69 maal zo groot in GeoJSON (expliciet) als in IFC (impliciet). 

| model | Bestandsgrootte IFC (KB) | Bestandsgrootte GeoJSON mapping (KB)*|  
|-|-|-|
| A20 Corridor    | 7.787     | 2.094  |   
| aisc_sculpture_param    | 314   | 4.206 |   
| ifcbridge-model01 | 14.817  | 26.049 |    
| ifcbridge-model04 | 55  | 296 |    
| ifcbridge-model05 | 25 | 205 | 
| tabel_chairs | 705 | 48.641 |
| kievitsweg_R25 | 13.706 | 65.386 |



# 3D Geometrie in standaarden 

Onderstaande tabellen laat een vergelijking zien tussen verschillende standaarden (ISO19107, GML, IFC, STEP, OpenCascade en WKT) voor het beschrijven van 2D en 3D geometrie. 

De tabellen maken zichtbaar dat GIS-systemen voornamelijk werken met expliciete geometrie. CAD/BIM-systemen werken met zowel expliciete als impliciete geometrie. 

De tabellen tonen de beperking van 1-op-1 mapping tussen verschillende geometrische modellen. Een IFC-entiteit zoals IfcSweptDiskSolid, kan binnen STEP vaak één-op-één worden gemapt naar SweptDiskSolid. Voor andere geometrische modellen geldt echter dat een dergelijke één-op-één mapping niet bestaat. Een conversie naar GML resulteert daarom in een geëxpliciteerde representatie, bijvoorbeeld als gml:MultiSurface. Hierbij gaat de oorspronkelijke constructieve opbouwinformatie verloren. Ook kan men geometrische kwaliteit verliezen, doordat analytische vormen worden benaderd door gediscretiseerde representaties.


<table>
  <caption>Punten</caption>
  <colgroup>
    <col style="width:16.66%">
    <col style="width:16.66%">
    <col style="width:16.66%">
    <col style="width:16.66%">
    <col style="width:16.66%">
    <col style="width:16.66%">
  </colgroup>
  <thead>
    <tr>
      <th>ISO 19107</th>
      <th>GML</th>
      <th>IFC</th>
      <th>STEP</th>
      <th>OpenCascade</th>
      <th>WKT</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td></td>
      <td></td>
      <td>
        <a href="https://standards.buildingsmart.org/IFC/RELEASE/IFC4_3/HTML/lexical/IfcCartesianPoint.htm">IfcCartesianPoint</a>
      </td>
      <td>
        <a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.cartesian_point">cartesian_point</a>
      </td>
      <td>
        <a href="https://dev.opencascade.org/doc/refman/html/class_geom2d___cartesian_point.html">Geom2d_CartesianPoint</a><br>
        <a href="https://dev.opencascade.org/doc/refman/html/class_geom___cartesian_point.html">Geom_CartesianPoint</a>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <a href="http://www.opengis.net/def/geometry/ISO-19107/2003/GM_Point">GM_Point</a>
      </td>
      <td>
        <a href="https://schemas.opengis.net/gml/3.2.1/geometryBasic0d1d.xsd">gml:Point</a>
      </td>
      <td></td>
      <td></td>
      <td>
        <a href="https://dev.opencascade.org/doc/refman/html/class_geom2d___point.html">Geom2d_Point</a><br>
        <a href="https://dev.opencascade.org/doc/refman/html/class_geom___point.html">Geom_Point</a>
      </td>
      <td>
        <a href="https://www.ogc.org/standards/sfa/">POINT (x y (z)(m))</a>
      </td>
    </tr>
    <tr>
      <td></td><td></td><td></td>
      <td>
        <a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.cylindrical_point">cylindrical_point</a>
      </td>
      <td></td><td></td>
    </tr>
    <tr>
      <td></td><td></td><td></td>
      <td>
        <a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.spherical_point">spherical_point</a>
      </td>
      <td></td><td></td>
    </tr>
    <tr>
      <td></td><td></td><td></td>
      <td>
        <a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.polar_point">polar_point</a>
      </td>
      <td></td><td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td>
        <a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcPointByDistanceExpression.htm">IfcPointByDistanceExpression</a>
      </td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td>
        <a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcPointOnCurve.htm">IfcPointOnCurve</a>
      </td>
      <td>
        <a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.point_on_curve">point_on_curve</a>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td>
        <a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcPointOnSurface.htm">IfcPointOnSurface</a>
      </td>
      <td>
        <a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.point_on_surface">point_on_surface</a>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td><td></td><td></td>
      <td>
        <a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.point_in_volum">point_in_volume</a>
      </td>
      <td></td><td></td>
    </tr>
    <tr>
      <td></td><td></td><td></td>
      <td>
        <a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.point_replica">point_replica</a>
      </td>
      <td></td><td></td>
    </tr>
    <tr>
      <td></td><td></td><td></td>
      <td>
        <a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.degenerate_pcurve">degenerate_pcurve</a>
      </td>
      <td></td><td></td>
    </tr>
    <tr>
      <td></td><td></td><td></td>
      <td>
        <a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.evaluated_degenerate_pcurv">evaluated_degenerate_pcurve</a>
      </td>
      <td></td><td></td>
    </tr>
  </tbody>
</table>

<table>
  <thead>
    <tr>
      <th>ISO 19107</th>
      <th>GML</th>
      <th>IFC</th>
      <th>STEP</th>
      <th>OpenCascade</th>
      <th>WKT</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>GM_Complex</td>
      <td>gml:GeometricComplex</td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td><a href="http://www.opengis.net/def/geometry/ISO-19107/2003/GM_CompositePoint">GM_CompositePoint</a></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td><a href="http://www.opengis.net/def/geometry/ISO-19107/2003/GM_CompositeCurve">GM_CompositeCurve</a></td>
      <td><a href="https://schemas.opengis.net/gml/3.2.1/geometryComplexes.xsd">gml:CompositeCurve</a></td>
      <td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcCompositeCurve.htm">IfcCompositeCurve</a></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.composite_curve">composite_curv</a></td>
      <td><a href="https://dev.opencascade.org/doc/refman/html/class_i_g_e_s_geom___composite_curve.html">composite_curve</a></td>
      <td>COMPOUNDCURVE(x y (z)(m))</td>
    </tr>
    <tr>
      <td><a href="http://www.opengis.net/def/geometry/ISO-19107/2003/GM_CompositeSurface">GM_CompositeSurface</a></td>
      <td><a href="https://schemas.opengis.net/gml/3.2.1/geometryComplexes.xsd">gml:CompositeSurface</a></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td><a href="http://www.opengis.net/def/geometry/ISO-19107/2003/GM_CompositeSolid">GM_CompositeSolid</a></td>
      <td><a href="https://schemas.opengis.net/gml/3.2.1/geometryPrimitives.xsd">gml:CompositeSolid</a></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.composite_curve_segment">composite_curve_segment</a></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.reparametrised_composite_curve_segment">reparametrised_composite_curve_segment</a></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.rectangular_composite_surface">rectangular_composite_surface</a></td>
      <td></td>
      <td></td>
    </tr>
  </tbody>
</table>


<table>
<caption>Lijnen</caption>
<thead>
<tr>
<th>ISO 19107</th>
<th>GML</th>
<th>IFC</th>
<th>STEP</th>
<th>OpenCascade</th>
<th>WKT</th>
</tr>
</thead>
<tbody>

<tr>
<td><a href="http://www.opengis.net/def/geometry/iso-19107/2003/gm_curve">GM_Curve</a></td>
<td><a href="https://schemas.opengis.net/gml/3.2.1/geometryBasic0d1d.xsd">gml:Curve</a></td>
<td></td><td></td><td></td><td></td>
</tr>

<tr>
<td><a href="http://www.opengis.net/def/geometry/ISO-19107/2003/GM_OrientableCurve">GM_OrientableCurve</a></td>
<td><a href="https://schemas.opengis.net/gml/3.2.1/geometryPrimitives.xsd">gml:OrientableCurve</a></td>
<td></td><td></td><td></td><td></td>
</tr>

<tr>
<td>GM_Arc</td>
<td><a href="https://schemas.opengis.net/gml/3.2.1/geometryPrimitives.xsd">gml:Arc</a></td>
<td></td><td></td><td></td>
<td><a href="https://www.ogc.org/standards/sfa/">CIRCULARSTRING(x y (z)(m))</a></td>
</tr>

<tr>
<td>GM_ArcByBulge</td>
<td><a href="https://schemas.opengis.net/gml/3.2.1/geometryPrimitives.xsd">gml:ArcByBulge</a></td>
<td></td><td></td><td></td><td></td>
</tr>

<tr>
<td>GM_ArcString</td>
<td><a href="https://schemas.opengis.net/gml/3.2.1/geometryPrimitives.xsd">gml:ArcString</a></td>
<td></td><td></td><td></td><td></td>
</tr>

<tr>
<td>GM_ArcStringByBulge</td>
<td><a href="https://schemas.opengis.net/gml/3.2.1/geometryPrimitives.xsd">gml:ArcStringByBulge</a></td>
<td></td><td></td><td></td><td></td>
</tr>

<tr>
<td></td>
<td><a href="https://schemas.opengis.net/gml/3.2.1/geometryPrimitives.xsd">gml:CircleByCenterPoint</a></td>
<td></td><td></td><td></td><td></td>
</tr>

<tr>
<td></td>
<td><a href="https://schemas.opengis.net/gml/3.2.1/geometryPrimitives.xsd">gml:CubicSpline</a></td>
<td></td><td></td><td></td><td></td>
</tr>

<tr>
<td></td>
<td><a href="https://schemas.opengis.net/gml/3.2.1/geometryPrimitives.xsd">gml:Knot</a></td>
<td></td><td></td><td></td><td></td>
</tr>

<tr>
<td></td>
<td>gml:AffinePlacement</td>
<td></td><td></td><td></td><td></td>
</tr>

<tr>
<td></td>
<td>gml:AbstractSurface</td>
<td></td><td></td><td></td><td></td>
</tr>

<tr>
<td></td>
<td><a href="https://schemas.opengis.net/gml/3.2.1/geometryBasic2d.xsd">gml:Polygon</a></td>
<td></td><td></td><td></td>
<td><a href="https://www.ogc.org/standards/sfa">POLYGON(x y (z)(m))</a></td>
</tr>

<tr>
<td>GM_Polygon</td>
<td><a href="https://schemas.opengis.net/gml/3.2.1/geometryPrimitives.xsd">gml:Polygonpatch</a></td>
<td></td><td></td><td></td><td></td>
</tr>

<tr>
<td><a href="http://www.opengis.net/def/geometry/ISO-19107/2003/GM_Ring">GM_Ring</a></td>
<td><a href="https://schemas.opengis.net/gml/3.2.1/geometryPrimitives.xsd">gml:Ring</a></td>
<td></td><td></td><td></td><td></td>
</tr>

<tr>
<td></td>
<td>gml:AbstractRing</td>
<td></td><td></td><td></td><td></td>
</tr>

<tr>
<td></td>
<td><a href="https://schemas.opengis.net/gml/3.2.1/geometryBasic2d.xsd">gml:LinearRing</a></td>
<td></td><td></td><td></td><td></td>
</tr>

<tr>
<td></td>
<td>gml:Surface</td>
<td></td><td></td><td></td><td></td>
</tr>

<tr>
<td></td>
<td>gml:Patches</td>
<td></td><td></td><td></td><td></td>
</tr>

<tr>
<td></td>
<td>gml:AbstractRing</td>
<td></td><td></td><td></td><td></td>
</tr>

<tr>
<td><a href="http://www.opengis.net/def/geometry/ISO-19107/2003/GM_OrientableSurface">GM_OrientableSurface</a></td>
<td><a href="https://schemas.opengis.net/gml/3.2.1/geometryPrimitives.xsd">gml:OrientableSurface</a></td>
<td></td><td></td><td></td><td></td>
</tr>

<tr>
<td></td>
<td><a href="https://schemas.opengis.net/gml/3.2.1/geometryPrimitives.xsd">gml:Bspline</a></td>
<td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcBSplineCurveWithKnots.htm">IfcBSplineCurveWithKnots</a></td>
<td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.b_spline_curve_with_knots">B_spline_curve_with_knots</a></td>
<td>
<a href="https://dev.opencascade.org/doc/refman/html/class_geom2d___b_spline_curve.html">Geom2d_BSplineCurve</a><br>
<a href="https://dev.opencascade.org/doc/refman/html/class_geom___b_spline_curve.html">Geom_BSplineCurve</a>
</td>
<td></td>
</tr>

<tr>
<td></td>
<td></td>
<td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcRationalBSplineCurveWithKnots.htm">IfcRationalBSplineCurveWithKnots</a></td>
<td></td><td></td><td></td>
</tr>

<tr>
<td>GM_Bezier</td>
<td><a href="https://schemas.opengis.net/gml/3.2.1/geometryPrimitives.xsd">gml:Bezier</a></td>
<td></td>
<td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.bezier_curve">bezier_curve</a></td>
<td>
<a href="https://dev.opencascade.org/doc/refman/html/class_geom2d___bezier_curve.html">Geom2D_BezierCurve</a><br>
<a href="https://dev.opencascade.org/doc/refman/html/class_geom___bezier_curve.html">Geom_BezierCurve</a>
</td>
<td></td>
</tr>

<tr>
<td></td><td></td><td></td>
<td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.rational_b_spline_curve">rational_b_spline_curve</a></td>
<td></td><td></td>
</tr>

<tr>
<td></td><td></td><td></td>
<td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.local_b_spline">local_b_spline</a></td>
<td></td><td></td>
</tr>

<tr>
<td></td><td></td><td></td>
<td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.uniform_curve">uniform_curve</a></td>
<td></td><td></td>
</tr>

<tr>
<td></td><td></td><td></td>
<td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.quasi_uniform_curve">quasi_uniform_curve</a></td>
<td></td><td></td>
</tr>

<tr>
<td></td><td></td><td></td>
<td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.locally_refined_spline_curve">locally_refined_spline_curve</a></td>
<td></td><td></td>
</tr>

<tr>
<td></td><td></td><td></td>
<td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.rational_locally_refined_spline_curve">rational_locally_refined_spline_curve</a></td>
<td></td><td></td>
</tr>

<tr>
<td></td><td></td><td></td>
<td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.trimmed_curve">trimmed_curve</a></td>
<td>
<a href="https://dev.opencascade.org/doc/refman/html/class_geom2d___trimmed_curve.html">Geom2d_TrimmedCurve</a><br>
<a href="https://dev.opencascade.org/doc/refman/html/class_geom___trimmed_curve.html">Geom_TrimmedCurve</a>
</td>
<td></td>
</tr>
<tr>
<td></td><td></td>
<td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcCompositeCurveOnSurface.htm">IfcCompositeCurveOnSurface</a></td>
<td></td><td></td><td></td>
</tr>

<tr>
<td></td><td></td>
<td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcBoundaryCurve.htm">IfcBoundaryCurve</a></td>
<td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.boundary_curve">boundary_curve</a></td>
<td></td><td></td>
</tr>

<tr>
<td></td><td></td>
<td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcOuterBoundaryCurve.htm">IfcOuterBoundaryCurve</a></td>
<td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.outer_boundary_curve">outer_boundary_curve</a></td>
<td></td><td></td>
</tr>

<tr>
<td></td><td></td>
<td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcGradientCurve.htm">IfcGradientCurve</a></td>
<td></td><td></td><td></td>
</tr>

<tr>
<td></td><td></td>
<td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcSegmentedReferenceCurve.htm">IfcSegmentedReferenceCurve</a></td>
<td></td><td></td><td></td>
</tr>

<tr>
<td></td><td></td>
<td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcIndexedPolyCurve.htm">IfcIndexedPolyCurve</a></td>
<td></td><td></td><td></td>
</tr>

<tr>
<td><a href="http://www.opengis.net/def/geometry/ISO-19107/2003/GM_LineString">GM_LineString</a></td>
<td>gml:LineStringSegment</td>
<td></td><td></td><td></td>
<td>LINESTRING(x y (z)(m))</td>
</tr>

<tr>
<td></td>
<td><a href="https://schemas.opengis.net/gml/3.2.1/geometryBasic0d1d.xsd">gml:LineString</a></td>
<td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcPolyline.htm">IfcPolyline</a></td>
<td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.polyline">polyline</a></td>
<td><a href="https://dev.opencascade.org/doc/refman/html/class_topo_d_s___wire.html">TopoDS_Wire</a></td>
<td></td>
</tr>

<tr>
<td></td><td></td>
<td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcTrimmedCurve.htm">IfcTrimmedCurve</a></td>
<td></td><td></td><td></td>
</tr>

<tr>
<td>GM_Circle</td>
<td><a href="https://schemas.opengis.net/gml/3.2.1/geometryPrimitives.xsd">gml:Circle</a></td>
<td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcCircle.htm">IfcCircle</a></td>
<td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.circle">circle</a></td>
<td>
<a href="https://dev.opencascade.org/doc/refman/html/class_geom2d___circle.html">Geom2d_Circle</a> +
<a href="https://dev.opencascade.org/doc/refman/html/class_geom___circle.html">Geom_Circle</a>
</td>
<td></td>
</tr>

<tr>
<td></td><td></td>
<td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcEllipse.htm">IfcElipse</a></td>
<td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.elipse">elipse</a></td>
<td>
<a href="https://dev.opencascade.org/doc/refman/html/class_geom2d___ellipse.html">Geom2d_Ellipse</a> +
<a href="https://dev.opencascade.org/doc/refman/html/class_geom___ellipse.html">Geom_Ellipse</a>
</td>
<td></td>
</tr>

<tr>
<td></td><td></td>
<td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcLine.htm">IfcLine</a></td>
<td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.line">line</a></td>
<td>
<a href="https://dev.opencascade.org/doc/refman/html/class_geom2d___line.html">Geom2d_Line</a> +
<a href="https://dev.opencascade.org/doc/refman/html/class_geom___line.html">Geom_Line</a>
</td>
<td></td>
</tr>

<tr>
<td></td><td></td><td></td>
<td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.hyperbola">hyperbola</a></td>
<td>
<a href="https://dev.opencascade.org/doc/refman/html/class_geom2d___hyperbola.html">Geom2d_Hyperbola</a> +
<a href="https://dev.opencascade.org/doc/refman/html/class_geom___hyperbola.html">Geom_Hyperbola</a>
</td>
<td></td>
</tr>

<tr>
<td></td><td></td><td></td>
<td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.parabola">parabola</a></td>
<td>
<a href="https://dev.opencascade.org/doc/refman/html/class_geom2d___parabola.html">Geom2d_Parabola</a> +
<a href="https://dev.opencascade.org/doc/refman/html/class_geom___parabola.html">Geom_Parabola</a>
</td>
<td></td>
</tr>

<tr>
      <td></td>
      <td>gml:OffsetCurve</td>
      <td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcOffsetCurve2D.htm">IfcOffsetCurve2D</a></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.offset_curve_2d">offset_curve_2d</a></td>
      <td>
        <a href="https://dev.opencascade.org/doc/refman/html/class_geom2d___offset_curve.html">Geom2d_OffsetCurve</a> +
        <a href="https://dev.opencascade.org/doc/refman/html/class_geom___offset_curve.html">Geom_OffsetCurve</a>
      </td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcOffsetCurve3D.htm">IfcOffsetCurve3D</a></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.offset_curve_3d">offset_curve_3d</a></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcOffsetCurveByDistances.htm">IfcOffsetCurveByDistances</a></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcPcurve.htm">IfcPcurve</a></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.pcurve">pcurve</a></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.bounded_pcurve">bounded_pcurve</a></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcPolynomialCurve.htm">IfcPolynomialCurve</a></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcClothoid.htm">IfcClothoid</a></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.clothoid">clothoid</a></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.circular_involute">circular_involute</a></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
  <td></td>
  <td></td>
  <td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcCosineSpiral.htm">IfcCosineSpiral</a></td>
  <td></td>
  <td></td>
  <td></td>
</tr>
<tr>
  <td></td>
  <td></td>
  <td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcSecondOrderPolynomialSpiral.htm">IfcSecondOrderPolynomialSpiral</a></td>
  <td></td>
  <td></td>
  <td></td>
</tr>
<tr>
  <td></td>
  <td></td>
  <td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcThirdOrderPolynomialSpiral.htm">IfcThirdOrderPolynomialSpiral</a></td>
  <td></td>
  <td></td>
  <td></td>
</tr>
<tr>
  <td></td>
  <td></td>
  <td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcSeventhOrderPolynomialSpiral.htm">IfcSeventhOrderPolynomialSpiral</a></td>
  <td></td>
  <td></td>
  <td></td>
</tr>
<tr>
  <td></td>
  <td></td>
  <td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcSineSpiral.htm">IfcSineSpiral</a></td>
  <td></td>
  <td></td>
  <td></td>
</tr>
<tr>
  <td></td>
  <td></td>
  <td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcSurfaceCurve.htm">IfcSurfaceCurve</a></td>
  <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.surface_curve">surface_curve</a></td>
  <td></td>
  <td></td>
</tr>
<tr>
  <td></td>
  <td></td>
  <td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcIntersectionCurve.htm">IfcIntersectionCurve</a></td>
  <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.intersection_curve">intersection_curve</a></td>
  <td></td>
  <td></td>
</tr>
<tr>
  <td></td>
  <td></td>
  <td></td>
  <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.seam_curve">seam_curve</a></td>
  <td></td>
  <td></td>
</tr>
<tr>
  <td></td>
  <td></td>
  <td></td>
  <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.bounded_surface_curve">bounded_surface_curve</a></td>
  <td></td>
  <td></td>
</tr>
<tr>
  <td></td>
  <td></td>
  <td></td>
  <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.composite_curve_on_surface">composite_curve_on_surface</a></td>
  <td></td>
  <td></td>
</tr>
<tr>
  <td></td>
  <td></td>
  <td></td>
  <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.curve_replica">curve_replica</a></td>
  <td></td>
  <td></td>
</tr>
<tr>
  <td></td>
  <td></td>
  <td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcSeamCurve.htm">IfcSeamCurve</a></td>
  <td></td>
  <td></td>
  <td></td>
</tr>
<tr>
  <td></td>
  <td></td>
  <td></td>
  <td></td>
  <td>
    <a href="https://dev.opencascade.org/doc/refman/html/class_geom2d___vector_with_magnitude.html">Geom2d_VectorWithMagnitude</a> +
    <a href="https://dev.opencascade.org/doc/refman/html/class_geom___vector_with_magnitude.html">Geom_VectorWithMagnitude</a>
  </td>
  <td></td>
</tr>
<tr>
  <td></td>
  <td></td>
  <td></td>
  <td></td>
  <td></td>
  <td>
    <a href="https://dev.opencascade.org/doc/refman/html/class_shape_extend___complex_curve.html">shapeExtend_ComplexCurve</a>
  </td>
</tr> 
</table>

<table>
  <thead>
    <tr>
      <th>ISO 19107</th>
      <th>GML</th>
      <th>IFC</th>
      <th>STEP</th>
      <th>OpenCascade</th>
      <th>WKT</th>
      <th>X3D</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="http://www.opengis.net/def/geometry/ISO-19107/2003/GM_Surfac">GM_Surface</a></td>
      <td><a href="https://schemas.opengis.net/gml/3.2.1/geometryPrimitives.xsd">gml:Surface</a></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>GM_PolyhedralSurface</td>
      <td><a href="https://schemas.opengis.net/gml/3.2.1/geometryPrimitives.xsd">gml:PolyhedralSurface</a></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>GM_TriangulatedSurface</td>
      <td><a href="https://schemas.opengis.net/gml/3.2.1/geometryPrimitives.xsd">gml:TriangulatedSurface</a></td>
      <td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcTriangulatedFaceSet.htm">IfcTriangulatedFaceSet</a></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/6_schema.htm#geometric_model_schema.triangulated_face">triangulated_face</a></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>GM_Tin</td>
      <td><a href="https://schemas.opengis.net/gml/3.2.1/geometryPrimitives.xsd">gml:Tin</a></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>GM_SurfacePatch</td>
      <td>gml:AbstractSurfacePatch</td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td><a href="https://schemas.opengis.net/gml/3.2.1/geometryPrimitives.xsd">gml:Triangle</a></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td><a href="https://schemas.opengis.net/gml/3.2.1/geometryPrimitives.xsd">gml:Rectangle</a></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>GM_PointGrid</td>
      <td><a href="https://schemas.opengis.net/gml/3.2.1/geometryPrimitives.xsd">gml:PointGrid</a></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>GM_ParametricCurveSurface</td>
      <td>gml:AbstractParametricCurveSurface</td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>GM_GriddedSurface</td>
      <td>gml:AbstractGriddedSurface</td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
      <tr>
      <td></td>
      <td></td>
      <td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcPlane.htm">IfcPlane</a></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.plane">plane</a></td>
      <td><a href="https://dev.opencascade.org/doc/refman/html/class_geom___plane.html">Geom_Plane</a></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcCylindricalSurface.htm">IfcCylindricalSurface</a></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.cylindrical_surface">cylindrical_surface</a></td>
      <td><a href="https://dev.opencascade.org/doc/refman/html/class_geom___cylindrical_surface.html">Geom_CylindricalSurface</a></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.conical_surface">conical_surface</a></td>
      <td><a href="https://dev.opencascade.org/doc/refman/html/class_geom___conical_surface.html">Geom_ConicalSurface</a></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcSphericalSurface.htm">IfcSphericalSurface</a></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.spherical_surface">spherical_surface</a></td>
      <td><a href="https://dev.opencascade.org/doc/refman/html/class_geom___spherical_surface.html">Geom_SphericalSurface</a></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcToroidalSurface.htm">IfcToroidalSurface</a></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.toroidal_surface">toroidal_surface</a></td>
      <td><a href="https://dev.opencascade.org/doc/refman/html/class_geom___toroidal_surface.html">Geom_ToroidalSurface</a></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.degenerate_toroidal_surface">degenerate_toroidal_surface</a></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.dupin_cyclide_surface">dupin_cyclide_surface</a></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcBSplineSurface.htm">IfcBSplineSurface</a></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.b_spline_surface">b_spline_surface</a></td>
      <td><a href="https://dev.opencascade.org/doc/refman/html/class_geom___b_spline_surface.html">Geom_BSplineSurface</a></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcBSplineSurfaceWithKnots.htm">IfcBSplineSurfaceWithKnots</a></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.b_spline_surface_with_knots">b_spline_surface_with_knots</a></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.uniform_surface">uniform_surface</a></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.uasi_uniform_surface">uasi_uniform_surface</a></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.bezier_surface">bezier_surface</a></td>
      <td><a href="https://dev.opencascade.org/doc/refman/html/class_geom___bezier_surface.html">Geom_BezierSurface</a></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.rational_b_spline_surface">rational_b_spline_surface</a></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.locally_refined_spline_surface">locally_refined_spline_surface</a></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.rational_locally_refined_spline_surface">rational_locally_refined_spline_surface</a></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcCurveBoundedPlane.htm">IfcCurveBoundedPlane</a> + <a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcCurveBoundedSurface.htm">IfcCurveBoundedSurface</a></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.curve_bounded_surface">curve_bounded_surface</a></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.surface_patch">surface_patch</a></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.offset_surface">offset_surface</a></td>
      <td><a href="https://dev.opencascade.org/doc/refman/html/class_geom___offset_surface.html">Geom_OffsetSurface</a></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.oriented_surface">oriented_surface</a></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.surface_replica">surface_replica</a></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td><a href="https://dev.opencascade.org/doc/refman/html/class_geom___surface.html">Geom_Surface</a></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td><a href="https://dev.opencascade.org/doc/refman/html/class_geom___osculating_surface.html">Geom_OsculatingSurface</a></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcRectangularTrimmedSurface.htm">IfcRectangularTrimmedSurface</a></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.rectangular_trimmed_surface">rectangular_trimmed_surface</a></td>
      <td><a href="https://dev.opencascade.org/doc/refman/html/class_geom___rectangular_trimmed_surface.html">Geom_RectangularTrimmedSurface</a></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcSectionedSurface.htm">IfcSectionedSurface</a></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
  </tbody>
</table>

<table>
  <thead>
    <tr>
      <th>ISO 19107</th>
      <th>GML</th>
      <th>IFC</th>
      <th>STEP</th>
      <th>OpenCascade</th>
      <th>WKT</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td></td>
      <td></td>
      <td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcBlock.htm">IfcBlock</a></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/6_schema.htm#geometric_model_schema.block">block</a></td>
      <td>
        <a href="https://dev.opencascade.org/doc/refman/html/class_topo_d_s___solid.html#a493006c38aec5e41b5e05d0aac0485d1">TopoDS_Solid</a> +
        <a href="https://dev.opencascade.org/doc/refman/html/class_b_rep_prim_a_p_i___make_box.html">(BRepPrimAPI_MakeBox)</a>
      </td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcRectangularPyramid.htm">IfcRectangularPyramid</a></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/6_schema.htm#geometric_model_schema.rectangular_pyramid">rectangular_pyramid</a></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>GM_Cone</td>
      <td><a href="https://schemas.opengis.net/gml/3.2.1/geometryPrimitives.xsd#gml:Cone">gml:Cone</a></td>
      <td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcRightCircularCone.htm">IfcRightCircularCone</a></td>
      <td>
        <a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/6_schema.htm#geometric_model_schema.right_circular_cone">right_circular_cone</a> +
        <a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/6_schema.htm#geometric_model_schema.eccentric_cone">eccentric_cone</a>
      </td>
      <td>
        <a href="https://dev.opencascade.org/doc/refman/html/class_topo_d_s___solid.html#a493006c38aec5e41b5e05d0aac0485d1">TopoDS_Solid</a> +
        <a href="https://dev.opencascade.org/doc/refman/html/class_b_rep_prim_a_p_i___make_cone.html">(BRepPrimAPI_MakeCone)</a>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>GM_Cylinder</td>
      <td><a href="https://schemas.opengis.net/gml/3.2.1/geometryPrimitives.xsd#gml:Cylinder">gml:Cylinder</a></td>
      <td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcRightCircularCylinder.htm">IfcRightCircularCylinder</a></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/6_schema.htm#geometric_model_schema.right_circular_cylinder">right_circular_cylinder</a></td>
      <td>
        <a href="https://dev.opencascade.org/doc/refman/html/class_topo_d_s___solid.html#a493006c38aec5e41b5e05d0aac0485d1">TopoDS_Solid</a> +
        <a href="https://dev.opencascade.org/doc/refman/html/class_b_rep_prim_a_p_i___make_cylinder.html">(BRepPrimAPI_MakeCylinder)</a>
      </td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/6_schema.htm#geometric_model_schema.ellipsoid">ellipsoid</a></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td>
        <a href="https://dev.opencascade.org/doc/refman/html/class_topo_d_s___solid.html#a493006c38aec5e41b5e05d0aac0485d1">TopoDS_Solid</a> +
        <a href="https://dev.opencascade.org/doc/refman/html/class_b_rep_prim_a_p_i___make_half_space.html">(BRepPrimAPI_MakeHalfSpace)</a>
      </td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td>
        <a href="https://dev.opencascade.org/doc/refman/html/class_topo_d_s___solid.html#a493006c38aec5e41b5e05d0aac0485d1">TopoDS_Solid</a> +
        <a href="https://dev.opencascade.org/doc/refman/html/class_b_rep_prim_a_p_i___make_prism.html">(BRepPrimAPI_MakePrism)</a>
      </td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td>
        <a href="https://dev.opencascade.org/doc/refman/html/class_topo_d_s___solid.html#a493006c38aec5e41b5e05d0aac0485d1">TopoDS_Solid</a> +
        <a href="https://dev.opencascade.org/doc/refman/html/class_b_rep_prim_a_p_i___make_revol.html">(BRepPrimAPI_MakeRevol)</a>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td>
        <a href="https://dev.opencascade.org/doc/refman/html/class_topo_d_s___solid.html#a493006c38aec5e41b5e05d0aac0485d1">TopoDS_Solid</a> +
        <a href="https://dev.opencascade.org/doc/refman/html/class_b_rep_prim_a_p_i___make_revolution.html">(BRepPrimAPI_MakeRevolution)</a>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>GM_Sphere</td>
      <td><a href="https://schemas.opengis.net/gml/3.2.1/geometryPrimitives.xsd#gml:Sphere">gml:Sphere</a></td>
      <td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcSphere.htm">IfcSphere</a></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/6_schema.htm#geometric_model_schema.sphere">sphere</a></td>
      <td>
        <a href="https://dev.opencascade.org/doc/refman/html/class_topo_d_s___solid.html#a493006c38aec5e41b5e05d0aac0485d1">TopoDS_Solid</a> +
        <a href="https://dev.opencascade.org/doc/refman/html/class_b_rep_prim_a_p_i___make_sphere.html">(BRepPrimAPI_MakeSphere)</a>
      </td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td>
        <a href="https://dev.opencascade.org/doc/refman/html/class_topo_d_s___solid.html#a493006c38aec5e41b5e05d0aac0485d1">TopoDS_Solid</a> +
        <a href="https://dev.opencascade.org/doc/refman/html/class_b_rep_offset_a_p_i___make_pipe.html">(BRepPrimAPI_MakePipe)</a>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td>
        <a href="https://dev.opencascade.org/doc/refman/html/class_topo_d_s___solid.html#a493006c38aec5e41b5e05d0aac0485d1">TopoDS_Solid</a> +
        <a href="https://dev.opencascade.org/doc/refman/html/class_b_rep_offset_a_p_i___make_pipe_shell.html">(BRepPrimAPI_MakePipeShell)</a>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/6_schema.htm#geometric_model_schema.torus">torus</a></td>
      <td>
        <a href="https://dev.opencascade.org/doc/refman/html/class_topo_d_s___solid.html#a493006c38aec5e41b5e05d0aac0485d1">TopoDS_Solid</a> +
        <a href="https://dev.opencascade.org/doc/refman/html/class_b_rep_prim_a_p_i___make_torus.html">(BRepPrimAPI_MakeTorus)</a>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/6_schema.htm#geometric_model_schema.right_angular_wedge">right_angular_wedge</a></td>
      <td>
        <a href="https://dev.opencascade.org/doc/refman/html/class_topo_d_s___solid.html#a493006c38aec5e41b5e05d0aac0485d1">TopoDS_Solid</a> +
        <a href="https://dev.opencascade.org/doc/refman/html/class_b_rep_prim_a_p_i___make_wedge.html">(BRepPrimAPI_MakeWedge)</a>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/6_schema.htm#geometric_model_schema.tetrahedron">tetrahedron</a></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/6_schema.htm#geometric_model_schema.convex_hexahedron">convex_hexahedron</a></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/6_schema.htm#geometric_model_schema.faceted_primitive">faceted_primitive</a></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
  </tbody>
</table>

<table>
  <thead>
    <tr>
      <th>ISO 19107</th>
      <th>GML</th>
      <th>IFC</th>
      <th>STEP</th>
      <th>OpenCascade</th>
      <th>WKT</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td></td>
      <td></td>
      <td>
        <a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcCsgSolid.htm">IfcCsgSolid</a>
      </td>
      <td>
        <a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/6_schema.htm#geometric_model_schema.csg_solid">Csg_solid</a>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td>
        <a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcBooleanResult.htm">IfcBooleanResult</a>
      </td>
      <td>
        <a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/6_schema.htm#geometric_model_schema.boolean_result">boolean_result</a>
      </td>
      <td>
        <a href="https://dev.opencascade.org/doc/refman/html/class_b_rep_algo_a_p_i___boolean_operation.html">BRepAlgoAPI_BooleanOperation</a>
      </td>
      <td></td>
    </tr>
  </tbody>
</table>

<table>
  <thead>
    <tr>
      <th>ISO 19107</th>
      <th>GML</th>
      <th>IFC</th>
      <th>STEP</th>
      <th>OpenCascade</th>
      <th>WKT</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td></td>
      <td>gml:AbstractSolid</td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td><a href="http://www.opengis.net/def/geometry/ISO-19107/2003/GM_Solid">GM_Solid</a></td>
      <td><a href="https://schemas.opengis.net/gml/3.2.1/geometryPrimitives.xsd">gml:Solid</a></td>
      <td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcFacetedBrep.htm">IfcFacetedBrep</a></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/6_schema.htm#geometric_model_schema.manifold_solid_brep">manifold_solid_brep</a></td>
      <td>TopoDS_Solid(TopoDS_Face)</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcFacetedBrepWithVoids.htm">IfcFacetedBrepWithVoids</a></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcAdvancedBrep.htm">IfcAdvancedBrep</a></td>
      <td><a href="https://steptools.com/stds/stp_aim/html/t_advanced_brep_shape_representation.html">advanced_brep_shape_representation</a></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcAdvancedBrepWithVoids.htm">IfcAdvancedBrepWithVoids</a></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcSectionedSolidHorizontal.htm">IfcSectionedSolidHorizontal</a></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcFixedReferenceSweptAreaSolid.htm">IfcFixedReferenceSweptAreaSolid</a></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcDirectrixDerivedReferenceSweptAreaSolid.htm">IfcDirectrixDerivedReferenceSweptAreaSolid</a></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcExtrudedAreaSolid.htm">IfcExtrudedAreaSolid</a></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/6_schema.htm#geometric_model_schema.extruded_area_solid">extruded_area_solid</a></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcExtrudedAreaSolidTapered.htm">IfcExtrudedAreaSolidTapered</a></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcRevolvedAreaSolid.htm">IfcRevolvedAreaSolid</a></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcRevolvedAreaSolidTapered.htm">IfcRevolvedAreaSolidTapered</a></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td><a href="http://www.opengis.net/def/geometry/ISO-19107/2003/GM_Shell">GM_Shell</a></td>
      <td><a href="https://schemas.opengis.net/gml/3.2.1/geometryPrimitives.xsd">gml:Shell</a></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/6_schema.htm#geometric_model_schema.solid_replica">solid_replica</a></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/6_schema.htm#geometric_model_schema.brep_2d">brep_2d</a></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcSectionedSpine.htm">IfcSectionedSpine</a></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/6_schema.htm#geometric_model_schema.sectioned_spine">sectioned_spine</a></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcBoxedHalfSpace.htm">IfcBoxedHalfSpace</a></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/6_schema.htm#geometric_model_schema.boxed_half_space">boxed_half_space</a></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcPolygonalBoundedHalfSpace.htm">IfcPolygonalBoundedHalfSpace</a></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/6_schema.htm#geometric_model_schema.tessellated_solid">tesselated_solid</a></td>
      <td></td>
      <td></td>
    </tr>
  </tbody>
</table>

<table>
  <thead>
    <tr>
      <th>ISO 19107</th>
      <th>GML</th>
      <th>IFC</th>
      <th>STEP</th>
      <th>OpenCascade</th>
      <th>WKT</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td></td>
      <td></td>
      <td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcSurfaceCurveSweptAreaSolid.htm">IfcSurfaceCurveSweptAreaSolid</a></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcSweptDiskSolid.htm">IfcSweptDiskSolid</a></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/6_schema.htm#geometric_model_schema.swept_disk_solid">swept_disk_solid</a></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcSweptDiskSolidPolygonal.htm">IfcSweptDiskSolidPolygonal</a></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/6_schema.htm#geometric_model_schema.swept_face_solid">swept_face_solid</a></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/6_schema.htm#geometric_model_schema.swept_area_solid">swept_area_solid</a></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcSurfaceOfLinearExtrusion.htm">IfcSurfaceOfLinearExtrusion</a></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.surface_of_linear_extrusion">surface_of_linear_extrusion</a></td>
      <td><a href="https://dev.opencascade.org/doc/refman/html/class_geom___surface_of_linear_extrusion.html">Geom_SurfaceOfLinearExtrusion</a></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcSurfaceOfRevolution.htm">IfcSurfaceOfRevolution</a></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.surface_of_revolution">surface_of_revolution</a></td>
      <td><a href="https://dev.opencascade.org/doc/refman/html/class_geom___surface_of_revolution.html">Geom_SurfaceOfRevolution</a></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcSweptSurface.htm">IfcSweptSurface</a></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.surface_curve_swept_surface">surface_curve_swept_surface</a></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.fixed_reference_swept_surface">fixed_reference_swept_surface</a></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/6_schema.htm#geometric_model_schema.revolved_face_solid">revolved_face_solid</a></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/6_schema.htm#geometric_model_schema.extruded_face_solid">extruded_face_solid</a></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/6_schema.htm#geometric_model_schema.surface_curve_swept_face_solid">surface_curve_swept_area_solid</a></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/6_schema.htm#geometric_model_schema.swept_disk_solid">swept_disk_solid</a></td>
      <td></td>
      <td></td>
    </tr>
  </tbody>
</table>

<table>
  <thead>
    <tr>
      <th>ISO 19107</th>
      <th>GML</th>
      <th>IFC</th>
      <th>STEP</th>
      <th>OpenCascade</th>
      <th>WKT</th>
      <th>X3D</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.block_volume">block_volume</a></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.pyramid_volume">pyramid_volume</a></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.eccentric_conical_volume">eccentric_conical_volume</a></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.spherical_volume">spherical_volume</a></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.ellipsoid_volume">ellipsoid_volume</a></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.cylindrical_volume">cylindrical_volume</a></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.wedge_volume">wedge_volume</a></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.tetrahedron_volume">tetrahedron_volume</a></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.hexahedron_volume">hexadron_volume</a></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.toroidal_volume">toroidal_volume</a></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.bezier_volume">bezier_volume</a></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.uniform_volume">uniform_volume</a></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.quasi_uniform_volume">quasi_uniform_volume</a></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.rational_b_spline_volume">rational_b_spline_volume</a></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/6_schema.htm#geometric_model_schema.trimmed_volume">trimmed_volume</a></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.locally_refined_spline_volume">locally_refined_spline_volume</a></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.rational_locally_refined_spline_volume">rational_locally_refined_spline_volume</a></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.b_spline_volume">b_spline_volume</a></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.b_spline_volume_with_knots">b_spline_volume_with_knots</a></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
  </tbody>
</table>

<table>
  <thead>
    <tr>
      <th>ISO 19107</th>
      <th>GML</th>
      <th>IFC</th>
      <th>STEP</th>
      <th>OpenCascade</th>
      <th>WKT</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td></td>
      <td></td>
      <td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcAxis1Placement.htm">IfcAxis1Placement</a></td>
      <td>axis1_placement</td>
      <td><a href="https://dev.opencascade.org/doc/refman/html/class_geom___axis1_placement.html">Geom_Axis1Placement</a></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td>
        <a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcAxis2Placement2D.htm">IfcAxis2Placement2D</a> + 
        <a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcAxis2Placement3D.htm">IfcAxis2Placement3D</a>
      </td>
      <td>
        <a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.axis2_placement_2d">axis2_placement_2d</a> + 
        <a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.axis2_placement_3d">axis2_placement_3d</a>
      </td>
      <td><a href="https://dev.opencascade.org/doc/refman/html/class_geom___axis2_placement.html">Geom_Axis2Placement</a></td>
      <td></td>
    </tr>
  </tbody>
</table>

<table>
  <thead>
    <tr>
      <th>ISO 19107</th>
      <th>GML</th>
      <th>IFC</th>
      <th>STEP</th>
      <th>OpenCascade</th>
      <th>WKT</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td></td>
      <td>gml:RectifiedGrid</td>
      <td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcGrid.htm">IfcGrid</a></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td><a href="https://schemas.opengis.net/gml/3.2.1/coverage.xsd#gml:RectifiedGridCoverage">gml:RectifiedGridCoverage</a></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td><a href="https://schemas.opengis.net/gml/3.2.1/coverage.xsd#gml:GridCoverage">gml:GridCoverage</a></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
  </tbody>
</table>

<table>
  <thead>
    <tr>
      <th>ISO 19107</th>
      <th>GML</th>
      <th>IFC</th>
      <th>STEP</th>
      <th>OpenCascade</th>
      <th>WKT</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.cartesian_transformation_operator">cartesian_transformation_operator</a></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcCartesianTransformationOperator3D.htm">IfcCartesianTransformationOperator3D</a></td>
      <td><a href="https://www.steptools.com/stds/smrl/data/resource_docs/geometric_and_topological_representation/sys/4_schema.htm#geometry_schema.cartesian_transformation_operator_3d">cartesian_transformation_operator_3d</a></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td>
        <a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcCartesianTransformationOperator2D.htm">IfcCartesianTransformationOperator2D</a> +
        <a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcCartesianTransformationOperator2DnonUniform.htm">IfcCartesianTransformationOperator2DnonUniform</a>
      </td>
      <td>cartesian_transformation_operator_2d</td>
      <td>gp_Trsf2d</td>
      <td></td>
    </tr>
  </tbody>
</table>

<table>
  <thead>
    <tr>
      <th>ISO 19107</th>
      <th>GML</th>
      <th>IFC</th>
      <th>STEP</th>
      <th>OpenCascade</th>
      <th>WKT</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="http://www.opengis.net/def/geometry/ISO-19107/2003/GM_MultiPoint">GM_MultiPoint</a></td>
      <td><a href="https://schemas.opengis.net/gml/3.2.1/geometryAggregates.xsd">gml:MultiPoint</a></td>
      <td></td>
      <td></td>
      <td></td>
      <td>MULTIPOINT</td>
    </tr>
    <tr>
      <td><a href="http://www.opengis.net/def/geometry/ISO-19107/2003/GM_MultiCurve">GM_MultiCurve</a></td>
      <td><a href="https://schemas.opengis.net/gml/3.2.1/geometryAggregates.xsd">gml:MultiCurve</a></td>
      <td></td>
      <td></td>
      <td></td>
      <td>MULTILINESTRING</td>
    </tr>
    <tr>
      <td><a href="http://www.opengis.net/def/geometry/ISO-19107/2003/GM_MultiSurface">GM_MultiSurface</a></td>
      <td><a href="https://schemas.opengis.net/gml/3.2.1/geometryAggregates.xsd">gml:MultiSurface</a></td>
      <td></td>
      <td></td>
      <td></td>
      <td>MULTIPOLYGON</td>
    </tr>
    <tr>
      <td><a href="http://www.opengis.net/def/geometry/ISO-19107/2003/GM_MultiSolid">GM_MultiSolid</a></td>
      <td><a href="https://schemas.opengis.net/gml/3.2.1/geometryAggregates.xsd">gml:MultiSolid</a></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcCartesianPointList2D.htm">IfcCartesianPointList2D</a></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td><a href="https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/lexical/IfcCartesianPointList3D.htm">IfcCartesianPointList3D</a></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
  </tbody>
</table>

<table>
  <thead>
    <tr>
      <th>ISO 19107</th>
      <th>GML</th>
      <th>IFC</th>
      <th>STEP</th>
      <th>OpenCascade</th>
      <th>WKT</th>
    </tr>
  </thead>
  <tbody>
    <tr><td>boundary:Geometry</td><td></td><td></td><td></td><td></td><td></td></tr>
    <tr><td>convexHull:Geometry</td><td></td><td></td><td></td><td></td><td></td></tr>
    <tr>
      <td>distance</td>
      <td></td>
      <td></td>
      <td></td>
      <td>
        gp_Circ::Distance() +<br>
        gp_Circ2d::Distance() +<br>
        gp_Lin::Distance(const gp_Pnt &theP) const +<br>
        gp_Lin::Distance(const gp_Lin &theOther) const +<br>
        gp_Lin2d::Distance(const gp_Pnt2d &theP) const +<br>
        gp_Lin2d::Distance(const gp_Lin2d &theOther) +<br>
        gp_Pln::Distance +<br>
        gp_Circ::Distance() +<br>
        etc
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr><td>buffer</td><td></td><td></td><td></td><td></td><td></td></tr>
    <tr><td>intersection</td><td></td><td></td><td></td><td>BRepClass_Intersector</td><td></td></tr>
    <tr><td>difference</td><td></td><td></td><td></td><td></td><td></td></tr>
    <tr><td>symDifference</td><td></td><td></td><td></td><td></td><td></td></tr>
    <tr><td>union</td><td></td><td></td><td></td><td></td><td></td></tr>
    <tr><td>contains</td><td></td><td></td><td></td><td>BRepClass3d_SolidClassifier</td><td></td></tr>
    <tr><td>crosses</td><td></td><td></td><td></td><td></td><td></td></tr>
    <tr><td>disjoint</td><td></td><td></td><td></td><td></td><td></td></tr>
    <tr><td>equals</td><td></td><td></td><td></td><td></td><td></td></tr>
    <tr><td>intersects</td><td></td><td></td><td></td><td></td><td></td></tr>
    <tr><td>overlaps</td><td></td><td></td><td></td><td></td><td></td></tr>
    <tr><td>touches</td><td></td><td></td><td></td><td></td><td></td></tr>
    <tr><td>within</td><td></td><td></td><td></td><td></td><td></td></tr>
    <tr><td>withinDistance</td><td></td><td></td><td></td><td></td><td></td></tr>
    <tr><td>relate</td><td></td><td></td><td></td><td></td><td></td></tr>
    <tr><td>3Dboundary:Geometry</td><td></td><td></td><td></td><td></td><td></td></tr>
    <tr><td>3DconvexHull:Geometry</td><td></td><td></td><td></td><td></td><td></td></tr>
    <tr><td>3Ddistance</td><td></td><td></td><td></td><td></td><td></td></tr>
    <tr><td>3Dbuffer</td><td></td><td></td><td></td><td></td><td></td></tr>
    <tr><td>3Dintersection</td><td></td><td></td><td></td><td>BRepClass3d_Intersector3d</td><td></td></tr>
    <tr><td>3Ddifference</td><td></td><td></td><td></td><td></td><td></td></tr>
    <tr><td>3DsymDifference</td><td></td><td></td><td></td><td></td><td></td></tr>
    <tr><td>3Dunion</td><td></td><td></td><td></td><td></td><td></td></tr>
    <tr><td>3Dcontains</td><td></td><td></td><td></td><td></td><td></td></tr>
    <tr><td>3Dcrosses</td><td></td><td></td><td></td><td></td><td></td></tr>
    <tr><td>3Ddisjoint</td><td></td><td></td><td></td><td></td><td></td></tr>
    <tr><td>3Dequals</td><td></td><td></td><td></td><td></td><td></td></tr>
    <tr><td>3Dintersects</td><td></td><td></td><td></td><td></td><td></td></tr>
    <tr><td>3Doverlaps</td><td></td><td></td><td></td><td></td><td></td></tr>
    <tr><td>3Dtouches</td><td></td><td></td><td></td><td></td><td></td></tr>
    <tr><td>3Dwithin</td><td></td><td></td><td></td><td></td><td></td></tr>
    <tr><td>3DwithinDistance</td><td></td><td></td><td></td><td></td><td></td></tr>
    <tr><td>3Drelate</td><td></td><td></td><td></td><td></td><td></td></tr>
  </tbody>
</table>

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

