<h2 id="3c7374726f6e673e666c657820636f6d70696c65723c2f7374726f6e673e"><strong>Flex Compiler</strong></h2>

<p>If compiling from flex sdk use:</p>

<pre>
<span style="font-family: courier new,courier;">/opt/flexsdk/bin/mxmlc -theme=/opt/flexsdk/frameworks/themes/Halo/halo.swc \
  &nbsp;-static-link-runtime-shared-libraries=true \
   -output filesender.swf filesender.mxml</span></pre>

<p>Otherwise you will have some clients unable to use the flash application.</p>

