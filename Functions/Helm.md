## Helm
* <function><a id="renderhelmchart"></a><b>fn</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">RenderHelmChart</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">IDictionary\<string, object\></span> path, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> namespace = <span style="color:#D70000; margin-right:1px">"default"</span>, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> releaseName = <span style="color:#D70000; margin-right:1px">"RELEASE"</span>) -> <span style="color:#87AF00">Task\<CommandResult\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Path /example may be /example/Chart.yaml with content:
apiVersion: v2
name: test
description: Test chart

With template file /example/templates/file1.yaml
hello: &quot;world&quot;  

</pre></function>
