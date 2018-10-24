---
description: You can create a vector layer that references one or more vector (.vec) file, which contains the data that defines the vectors to be drawn on the globe.
seo-description: You can create a vector layer that references one or more vector (.vec) file, which contains the data that defines the vectors to be drawn on the globe.
seo-title: Define vector layers referencing vector files
solution: Analytics
title: Define vector layers referencing vector files
topic: Data workbench
uuid: 8dc54e33-a151-4131-82bb-eac17df76198
index: y
internal: n
snippet: y
---

# Define vector layers referencing vector files

You can create a vector layer that references one or more vector (.vec) file, which contains the data that defines the vectors to be drawn on the globe.

To define a vector layer that references one or more [!DNL .vec] files, you must have the following:

* **One or more [!DNL .vec] files** that contain the data used to draw the vectors on the globe.

  >[!NOTE]
  >
  >To obtain [!DNL .vec] files to use with your vector layers, contact Adobe.

* **A layer file** that specifies the location of the [!DNL .vec] files. For more information about the required format of the layer file, see [Vector Layer File Format](../../../data-workbench-client/c-im-layers/c-vctr-layers/c-ref-vctr-files.md#section_83A0077CF0C8479B9E7B2939BC761AF1).

  >[!NOTE]
  >
  >The [!DNL Boundaries.layer] file, provided with the [!UICONTROL Geography] profile, is a vector layer that references the [!DNL mwnation.vec], [!DNL mwstate.vec], [!DNL mwcoast.vec], [!DNL mwlake.vec], and [!DNL mwisland.vec] files.

## Vector layer file format {#section_83A0077CF0C8479B9E7B2939BC761AF1}

Each vector layer file referencing [!DNL .vec] files must be formatted using the following template: 

```
Layer = VectorLayer:
  Vec Files = vector: n items
    0 = string: Maps\\.vec file 1
    1 = string: Maps\\.vec file 2
    . . .
    n-1 = string: Maps\\.vec file n
  Color = v3d: color vector
  Alpha = double: alpha
  Width = double: width
  Error Factor = double: error factor
```

|  Parameter  | Description  |
|---|---|
|  Vec Files  |Path(s) to the [!DNL .vec] file(s) containing the vector data.  |
|  Color  | The RGB color vector, which is expressed as (red,green,blue). For each color in the vector, you can enter a value from 0.0 to 1.0. For example, (1.0, 0.0, 0.0) is bright red, and (0.5, 0.5, 0.5) is gray.  |
|  Alpha  | Controls the transparency of the vectors shown on the globe. The range is 0 to 1, with 0 being the most transparent.  |
|  Width  | Optional. Sets the width of the data in pixels. The recommended range is 1 to 4.  |
|  Error Factor  | Controls how accurately the vectors are drawn. For larger values, the vectors are drawn less accurately but faster. The default value is 5.  |

The [!DNL Boundaries.layer] file is formatted as follows: 

```
 Boundaries.layer file is formatted as follows:
Layer = VectorLayer:
  Vec Files = vector: 5 items
    0 = string: Maps\\mwnation.vec
    1 = string: Maps\\mwstate.vec
    2 = string: Maps\\mwcoast.vec
    3 = string: Maps\\mwlake.vec
    4 = string: Maps\\mwisland.vec
  Color = v3d: (.5,.5,1)
  Alpha = double: .5
  Error Factor = double: 4
```

