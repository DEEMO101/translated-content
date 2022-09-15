---
title: stroke
slug: Web/SVG/Attribute/stroke
tags:
  - Atributo SVG
  - SVG
translation_of: Web/SVG/Attribute/stroke
---
<div>{{SVGRef}}</div>

<p>O atributo <code><strong>stroke</strong></code> é um atributo de apresentação que define a cor <em>(ou qualquer SVG</em> <em>paint servers, como gradientes ou </em> <em>patterns</em><em>)</em> usado para pintar o contorno da forma;</p>

<p class="note"><strong>Note:</strong> As a presentation attribute <code>stroke</code> can be used as a CSS property.</p>

<p>As a presentation attribute, it can be applied to any element but it has effect only on the following twelve elements: {{SVGElement('altGlyph')}}, {{SVGElement('circle')}}, {{SVGElement('ellipse')}}, {{SVGElement('line')}}, {{SVGElement('path')}}, {{SVGElement('polygon')}}, {{SVGElement('polyline')}}, {{SVGElement('rect')}}, {{SVGElement('text')}}, {{SVGElement('textPath')}}, {{SVGElement('tref')}}, and {{SVGElement('tspan')}}</p>

<div id="topExample">
<div class="hidden">
<pre class="brush: css">html,body,svg { height:100% }</pre>
</div>

<pre class="brush: html">&lt;svg viewBox="0 0 20 10" xmlns="http://www.w3.org/2000/svg"&gt;
  &lt;!-- Simple color stroke --&gt;
  &lt;circle cx="5" cy="5" r="4" fill="none"
          stroke="green" /&gt;

  &lt;!-- Stroke a circle with a gradient --&gt;
  &lt;defs&gt;
    &lt;linearGradient id="myGradient"&gt;
      &lt;stop offset="0%"   stop-color="green" /&gt;
      &lt;stop offset="100%" stop-color="white" /&gt;
    &lt;/linearGradient&gt;
  &lt;/defs&gt;

  &lt;circle cx="15" cy="5" r="4" fill="none"
          stroke="url(#myGradient)" /&gt;
&lt;/svg&gt;
</pre>

<p>{{EmbedLiveSample('topExample', '100%', 200)}}</p>
</div>

<h2 id="Usage_notes">Usage notes</h2>

<table class="standard-table">
 <tbody>
  <tr>
   <th scope="row">Value</th>
   <td><strong><a href="/docs/Web/SVG/Content_type#Paint">&lt;paint&gt;</a></strong></td>
  </tr>
  <tr>
   <th scope="row">Default value</th>
   <td><code>none</code></td>
  </tr>
  <tr>
   <th scope="row">Animatable</th>
   <td>Yes</td>
  </tr>
 </tbody>
</table>

<h2 id="Specifications">Specifications</h2>

<table class="standard-table">
 <thead>
  <tr>
   <th scope="col">Specification</th>
   <th scope="col">Status</th>
   <th scope="col">Comment</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td>{{SpecName("SVG2", "painting.html#StrokeProperty", "stroke")}}</td>
   <td>{{Spec2("SVG2")}}</td>
   <td>Definition for shapes and texts.<br>
    Adds <code style="white-space: nowrap;">context-fill</code> and <code style="white-space: nowrap;">context-stroke</code>.</td>
  </tr>
  <tr>
   <td>{{SpecName("SVG1.1", "painting.html#StrokeProperty", "stroke")}}</td>
   <td>{{Spec2("SVG1.1")}}</td>
   <td>Initial definition for shapes and texts</td>
  </tr>
 </tbody>
</table>

<h2 id="Browser_Compatibility" name="Browser_Compatibility">Browser compatibility</h2>



<p>{{Compat("svg.attributes.presentation.stroke")}}</p>

<p class="note"><strong>Note:</strong> For information on using the <code style="white-space: nowrap;">context-stroke</code> (and <code style="white-space: nowrap;">context-fill</code>) values from HTML documents, see the documentation for the non-standard <span style="white-space: nowrap;">{{cssxref("-moz-context-properties")}}</span> property.</p>