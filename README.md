# C4-PlantUML

![Container diagram for Internet Banking System](http://www.plantuml.com/plantuml/png/bLJ1Rjj64BthAwRk8Gf0MoZIKq-H9Q5sAjbgADVfYHWkHz8YorrYPob5AFhldQKfKPG3kBcHmvdtthvvouySq8UwD8EVj5McBgZs1hOXLFpRQEHnVxFHOLldDPDNpWQouKQvSXGy8TUUFdmOJNwzNXgquMan7vN8WRoKieaqexRaRwg8_WvgAtEbp4FO4goTCMwlxGQCD07Q0dgVjMTvSY2yO9n2Omw2STG8hma6y_7VZq-hRFMupAQFpm-3TsrXd6Rf7xFLvExOyNo_kilcizzd3zFX-y4Ww608JcXGQDnuB4MXXtiRo5iAS8lsQnIR7ZXGEHWioREpGrLpS2Nv12Qdfwin7ClWrirfSfbEO2z6GjKCecbgW4gvsWQ-4XqlqDcj50hqXw7wHR0k1LozXty60D3f7Uufpx2gfFcPSXXNbT4AWtRsIagVS8S9f9MFuXT_JM9jIaRlH4OZZOFqAcXN6_VGb4-y-V7Wox68x3DpXGANocT3rqlSK6G_igRAwoeaCBQRsg2FvQLtErqG0nhpVPQrX2HAHwF38QvVrOsH33kDSKHxaFD2xjsUoRzILBfS6shjMCINawR9pmbymHB5YRuMCBhKWGhWEcSAihF_hOrVYNiH00NjjA9BUTDyM63079dY6jh7g2RzSmwzz-0ySGo_1qyRpS6ZK8EsaigosMu2MsHHZRMaIdago0QDXfCOAc86upRoGa7TlB8fH_MLR24-wPZNvVttOpDrqkQxkPvlR_WJBH5WeVxt5EtPjp2a4hN9k2a8tEnw8U_jjOhuAx5UDz1eOA6LT-pM0MRVr1RjXk1bKc3FC5i57QfWshN7aYxkxPcrQCnnqqeAnrESEmoOkpfqQqvErpM1uD4oDkVjJ1vy9dFsI-WkvXCJH-wxrMgPIcE_ZojyiwSNxDZQqcKFf3VRt7M_WGQkk-GjKbFih_r8Y7omAe5FwUF3w9oye_p1oUnMkZjXNUJxA9y92uQrTsNprzbx7OWXk8ZS0azl9m9vmZppuo96gS0oq7MiDXYTa5xY-XekvsgM17JqwMAr5A2UoxtnVkuwOvhvKUlEbyNyPCv76QrByny0 "Container diagram for Internet Banking System")

C4-PlantUML combines the benefits of [PlantUML](http://en.plantuml.com/) and the [C4 model](https://c4model.com/) for providing a simple way of describing and communicate software architectures - especially during up-front design sessions - with an intuitive language using open source and platform independent tools.

C4-PlantUML includes macros, stereotypes, and other goodies (like VSCode Snippets) for creating C4 diagrams with PlantUML.

- [C4-PlantUML](#c4-plantuml)
  - [Getting Started](#getting-started)
  - [Supported Diagram Types](#supported-diagram-types)
  - [Snippets for Visual Studio Code](#snippets-for-visual-studio-code)
  - [Layout Options](#layout-options)
  - [Advanced Samples](#advanced-samples)
    - [techtribes.js](#techtribesjs)
    - [Message Bus and Microservices](#message-bus-and-microservices)
  - [Background](#background)
  - [License](#license)

## Getting Started

At the top of your C4 PlantUML `.puml` file, you need to include the `C4_Context.puml`, `C4_Container.puml` or `C4_Component.puml` file found in the `root` of this repo.

To be independent of any internet connectifity, you can also download the files found in the `root` and reference it locally with

```csharp
!include path/to/C4_Container.puml
```

Just remember to change the `!include` statements inside the top of the files.

If you want to use the always up-to-date version in this repo, use the following:

```csharp
!includeurl https://raw.githubusercontent.com/treasure33/C4-PlantUML/release/1-0/C4_Container.puml
```

Now let's create a C4 Container diagram:

After you have included `C4_Container.puml` you can use the defined macro definitions for the C4 elements: `Person`, `Person_Ext`, `System`, `System_Ext`, `Container`, `Relationship`, `Boundary`, and `System_Boundary`

```csharp
@startuml C4_Elements
!includeurl https://raw.githubusercontent.com/treasure33/C4-PlantUML/release/1-0/C4_Container.puml

Person(personAlias, "Label", "Optional Description")
Container(containerAlias, "Label", "Technology", "Optional Description")
System(systemAlias, "Label", "Optional Description")

Rel(personAlias, containerAlias, "Label", "Optional Technology")
@enduml
```

![C4_Elements](http://www.plantuml.com/plantuml/png/ZKzDIyD04BtlhuWvfM2pIdloL8dUAXO_pcMw7Pg5oMoOcKNwxrq21aMKdjxRnxwFsQY1M1wewjRxHy81sTHTHGwKZvY5gjvir3ll1JxQKxG-7xAYXCHMlhOX3Tu4GRFWQkMxzN97mFR-jFM2L7JqjykRek-xue38AErOwfpReMZYPfpWdYBeTLLluO1K5_8yMamCL3sW1edJgrwuEQG9N-oNzGr3pudIwVnFqEjP3OT69xYqtRqW_HpyzuevujkSXTiW7ylrdm00 "C4_Elements")

In addition to this, it is also possible to define a system or component boundary.

Take a look a look at the following sample of a C4 Container Diagram:

```csharp
@startuml Basic Sample
!includeurl https://raw.githubusercontent.com/treasure33/C4-PlantUML/release/1-0/C4_Container.puml

Person(admin, "Administrator")
System_Boundary(c1, "Sample System") {
    Container(web_app, "Web Application", "C#, ASP.NET Core 2.1 MVC", "Allows users to compare multiple Twitter timelines")
}
System(twitter, "Twitter")

Rel(admin, web_app, "Uses", "HTTPS")
Rel(web_app, twitter, "Gets tweets from", "HTTPS")
@enduml
```

![Basic Sample](http://www.plantuml.com/plantuml/png/JOzFZzf03CNl-HHkUWaI9ANqr1CXgjf3gQ8cj4Sq9DvbfFapydWKeTL-ztK42piNQ_n-ptxUHbR4oHhOgQW7w9GD1hDFsWqcZPZ8m9avnEzLHMegdpMVqob5fC4xHiVbu6t5X2ecmiscQhwjMgCS7_Q_Aq8ZVQpMgo_IFpRYKDeXbK7sPLcB5Bqhr6YrMq9UprL79iMUyaNMNIAZFUvySgEYIp6i1Rh6WwkMB-0b0tdtoSM4fwCAGSZ_U88w1AC7nTgxN5hDvoNKNLl--T6BXH2-bclO_sjchJR6Jn7cooAm1pahA45iCgpdbVsacP60jKKZkw94VBs5BFWgofmR9cBs5ytxSOzOXoXEgR_wlks4cg6x-XZp4pdA5-VoHDv-j6pHZScQDm00 "Basic Sample")

## Supported Diagram Types

* System Context & System Landscape diagrams
  * Import: `!includeurl https://raw.githubusercontent.com/treasure33/C4-PlantUML/release/1-0/C4_Context.puml`
  * Macros: `Person`, `Person_Ext`, `System`, `System_Ext`, `SystemDb`, `SystemDb_Ext`, `Boundary`, `System_Boundary`, `Enterprise_Boundary`
* Container diagram
  * Import: `!includeurl https://raw.githubusercontent.com/treasure33/C4-PlantUML/release/1-0/C4_Container.puml`
  * Additional Macros: `Container`, `ContainerDb`, `Container_Boundary`
* Component diagram
  * Import: `!includeurl https://raw.githubusercontent.com/treasure33/C4-PlantUML/release/1-0/C4_Component.puml`
  * Additional Macros: `Component`, `ComponentDb`

Take a look at each of the [C4 Model Diagram Samples](samples/C4CoreDiagrams.md).

## Snippets for Visual Studio Code

Because the PlantUML support inside of Visual Studio Code is excellent with the [PlantUML extension](https://marketplace.visualstudio.com/items?itemName=jebbs.plantuml), you can also find VS Code snippets for C4-PlantUML at [.vscode/C4.code-snippets](.vscode/C4.code-snippets).

Project level snippets are now supported in [VSCode 1.28](https://code.visualstudio.com/updates/v1_28#_project-level-snippets).
Just include the `C4.code-snippets` file in the `.vscode` folder of your project.

It is possible to save them directly inside VS Code: [Creating your own snippets](https://code.visualstudio.com/docs/editor/userdefinedsnippets#_creating-your-own-snippets).

![C4-PlantUML Snippets Video](images/vscode_c4plantuml_snippets.gif)

## Layout Options

C4-PlantUML also comes with some layout options to make it easy and reuseable to create nice and useful diagrams:

* [LAYOUT_TOP_DOWN or LAYOUT_LEFT_RIGHT](LayoutOptions.md#layout_top_down-or-layout_left_right)
* [LAYOUT_WITH_LEGEND](LayoutOptions.md#layout_with_legend)
* [LAYOUT_AS_SKETCH](LayoutOptions.md#layout_as_sketch)

## Advanced Samples

The following advanced samples are reproductions with C4-PlantUML from official [C4 model samples](https://c4model.com/#examples) created by [Simon Brown](http://simonbrown.je/).

The core diagram samples from [c4model.com](https://c4model.com/#coreDiagrams) are available [here](samples/C4CoreDiagrams.md).

### techtribes.js

Source: [C4_Container Diagram Sample - techtribesjs.puml](samples/C4_Container%20Diagram%20Sample%20-%20techtribesjs.puml)

![techtribesjs](http://www.plantuml.com/plantuml/png/ZLJVS-B63t_tNw4lBqTc_8Mxq6jc-dG4qkIkv4U3QQPFdhKjOA_hNNTN3c4w_T-hNOF1eJEK1soaZwIFf8_uuaXOgai5FS9yJLPcwBwxNlG_gNDL5rXR1MkYolqq75gn6QmahUkiTcXpemar3N9J3icYSBN5qMWu-U7_JqfeMjpFXgLmX9PDwOJ1GcgqWugBHH-WrXnNSZpG6c5fb38RgLUW60H25z1nI-lupG3N1MLoeTIMS-mvmcc1Q3R-_N6HfCdZKpfzV7c8FkmCutaw_-KccTpj4IzVaxjqTdDxyp3jNqHHz8JM6PtUl55VQAEtfQbTwlkDeJVU6s31Xjx53jmNgvN5bI0iMcHhUGyjIgcb8oj86jt2EzPzI3JVEi8olJQrBeJTzlDFyV6U1hoeYxyYu4_uQcVGts2MYgfYz0jcCAug9VEGkiUcR-9Ln32lh9_t_M-J619JiXkk1c_UF_QxSE2fEJ_qLuaRgD1K2cDeAiUmstuC-CeFDdmt6NyZvGDOMbE6lOLLWISSGo5PEaA5tNvDm65EnZVPPJxD-XPLMcJCunbLuCn1Kq4Y4muzlVlj_DSPV1vyRjZEEGsw4txX2IMM6NUnbXLRXFh3lUURYMBbuRUIxkeCB5PcryK9jVvIAdHX8rpsP_u1pNvw_kSu6LqUqN4eRBu6gGjyG_TlRMhZ_bGSy62udT0WXDZGej4hCxs6oy5bfyamsEVvV3WcVbaY5WxwcJ8hODhaBi9mQOD8xfH-NHM2WjeMpTjU2t3bKSuez4hfjG07bJMXwNYNj3idNssl0p0Q1BXyZKMji01UblGS_cv5x0-ADf8Q2adpneWZT_FVmjwcIjVfstJik-Pdw2vYVPoSw47u2uVEztAN94zpnZEwUwVduTrRFHiIObhtaOn5qQmk36nZfHyj6H_Agnz-crvFuh1068q-_iY9EdawgZlaUWyBSkeYZeIqaHRzDidaHlbYbk3owkEdgntjTD7AunnnHeapx3lfElnVskPFSA61C-Fwh-qSiXuKTulK2XgaNXfRXhKUtKoeUhpHJgg3EXdQpP2Pcg2gCoLpo4s1pNr8CbRYcQnxMVkaxJ7LJkgLF_H0hZtsRYhVwqniq-Vs7_CmQdPzGLtKfVe7 "techtribesjs")

### Message Bus and Microservices

Source: [C4_Container Diagram Sample - message bus.puml](samples/C4_Container%20Diagram%20Sample%20-%20message%20bus.puml)

![messagebus](http://www.plantuml.com/plantuml/png/bLHBSzis4BxpLspLGvmPnygZfvuYIvewgMmfeZoUdZXBS2LX308OFEGgdVxt0gI5G3Kpa-WW0il5zzZ5ygDrQ9nl1OnglgjHFch1HiKlN3BX6_96mDuvRNyVZmq-NUsus_lQMp9CIKVINJ7LZfqXjDxGXm_ZwMzlLWAbkxzTZ5kqZam8LTEGZ5oIkTA1gdW5NePpRJWFRa-mLKAe9ovt848Ie6pWx3KtDgmK15uGYg4Gnu1nqWWl2GhxoAL6Woqy6TGFl75xUF_sRHPlyUzRiXPtLFAlrBqi5fE_blURQhDSLRFbmrtnwZamAQlop_bcUdFAUFYqkQaMyp_cTxEBrqLHhCXO9I-OjqwrP2vXcbQZ2Pp2ev1Q7gsZjhfMNZPeZXViNKWvPSCdkLMcHSUL7Bs6Vue2mYzvkq2jy-o9reApFZl4F-C1BJDSkqkOo9qNQ69u4cjhamWR2zcY3CPZSRa1RTIM2mhgpkcIdSgIEN16ENVPXqwybr1g4njuhPIBmSsUG2ik7QWj86DaBGHlIGRmpEeBvhRlJ5Lx6x2U-mJNtaReDTOrTxTVEXg3qcfbN0SUqhcCJ7GWwUnBN4CnD-ZCBArFiTpJsjV7-9mQGaSMPDGgkAK66dJOiIKmqDvePMc047t3NKOsYVkSQFhh-EfkledBbL47tWGoPNOekUrgy-OfX232T4nRP5o4vG3NhFxMiAREUpL3XpNQZczfa0c2T-zPt9LE6R8_rfI0dnn7WhnoESFjiVoooC3nLBolrC21Z0tWtQKG8ZNiMr6nWRrYFrFRm99LDkuY-Vn0CcsJbimVOAsyUxufuFReO8y72dzQawGcyFrR56iIsLJtytSVrOJdpMQpAaDQJAhM_N0EZCoz3kQ-KsI8_dSH3ErHialuN2xlncV0Yu4nx7MK91kR3AY8ya1rgTWZkN2wKpLmE9kj19Aq-Kvi1jhX3A3aLosLj-iYxpz6i-lfiuNpQHuOmHyKaSFq4_5J41t607iA3LhfgV_7bjsyTEB4rPqf5dYiraDiPqWXyMFGxLln7m00 "messagebus")

## Background

[PlantUML](http://en.plantuml.com/) is an open source project that allows you to create UML diagrams.
Diagrams are defined using a simple and intuitive language.
Images can be generated in PNG, in SVG or in LaTeX format.

PlantUML was created to allow the drawing of UML diagrams, using a simple and human readable text description.
Because it does not prevent you from drawing inconsistent diagrams, it is a drawing tool and not a modeling tool.
It is the most used text-based diagram drawing tool with [extensive support into wikis and forums, text editors and IDEs, use by different programming languages and documentation generators](http://en.plantuml.com/running).

The [C4 model](https://c4model.com/) for software architecture is an "abstraction-first" approach to diagramming, based upon abstractions that reflect how software architects and developers think about and build software.
The small set of abstractions and diagram types makes the C4 model easy to learn and use.
C4 stands for context, containers, components, and code — a set of hierarchical diagrams that you can use to describe your software architecture at different zoom levels, each useful for different audiences.

The C4 model was created as a way to help software development teams describe and communicate software architecture, both during up-front design sessions and when retrospectively documenting an existing codebase.

More information can be found here:

* [The C4 model for software architecture](https://c4model.com/)
* [REAL WORLD PlantUML - Sample Gallery](https://real-world-plantuml.com/)
* [Visualising and documenting software architecture cheat sheets](http://www.codingthearchitecture.com/2017/04/27/visualising_and_documenting_software_architecture_cheat_sheets.html)
* [PlantUML and Structurizr - Create models not diagrams](http://www.codingthearchitecture.com/2016/12/08/plantuml_and_structurizr.html)

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details