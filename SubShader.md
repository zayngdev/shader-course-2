### SubShader

A Shader object contains one or more SubShaders. SubShaders let you define different GPU settings and shader programs for different hardware, render pipelines, and runtime settings. Some Shader objects contain only a single SubShader; others contain multiple SubShaders to support a range of different configurations.

In ShaderLab, you define a SubShader by placing a `SubShader` block inside a `Shader` block.

Inside the `SubShader` block, you can:

- Assign a LOD  (level of detail) value to the SubShader, using the `LOD` block. 
- Assign key-value pairs of data to the SubShader, using the `Tags` block.
- Add GPU instructions or shader code to the SubShader, using ShaderLab commands. 
- Define one or more Passes, using the `Pass` block. 

This is the SubShader signature:

```
SubShader
{
    [LOD]
    [Tags]
    [Commands]
    Passes
}
```

This example code demonstrates the syntax for creating a Shader object that contains a single **SubShader**, which in turn contains a single Pass.

```
Shader "Examples/SinglePass"
{
    SubShader
    {
        Tags { "ExampleSubShaderTagKey" = "ExampleSubShaderTagValue" }
        LOD 100

        // ShaderLab commands that apply to the whole SubShader go here. 

        Pass
        {                
            Name "ExamplePassName"
            Tags { "ExamplePassTagKey" = "ExamplePassTagValue" }

            // ShaderLab commands that apply to this Pass go here.

            // HLSL code goes here.
        }
    }
}
```