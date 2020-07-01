# Layout Options

PlantUML uses [Graphviz](https://www.graphviz.org/) for his graph visualization. Thus the rendering itself is done automatically for you - that it one of the biggest advantages of using PlantUML.

...and also sometimes one of the biggest disadvantages, if the rendering is not what the user intended.

For this reason, C4-PlantUML also comes with some layout options.

## LAYOUT_TOP_DOWN or LAYOUT_LEFT_RIGHT

With the two macros `LAYOUT_TOP_DOWN` and `LAYOUT_LEFT_RIGHT` it is possible to easily change the flow visualization of the diagram. `LAYOUT_TOP_DOWN` is the default.

```csharp
@startuml LAYOUT_TOP_DOWN Sample
!includeurl https://raw.githubusercontent.com/treasure33/C4-PlantUML/master/C4_Container.puml

/' Not needed because this is the default '/
LAYOUT_TOP_DOWN

Person(admin, "Administrator")
System_Boundary(c1, 'Sample') {
    Container(web_app, "Web Application", "C#, ASP.NET Core 2.1 MVC", "Allows users to compare multiple Twitter timelines")
}
System(twitter, "Twitter")

Rel(admin, web_app, "Uses", "HTTPS")
Rel(web_app, twitter, "Gets tweets from", "HTTPS")
@enduml
```

![LAYOUT_TOP_DOWN Sample](http://www.plantuml.com/plantuml/png/NL1DZzCm4BtxLmpbaAnK4YtBYTE6WE2mRIEIKd6Ad6HABVd3iiUAAiH_PwAM5cqkJ_5xyzwRUOua0oMZuQNwkTjtVRTh-i-xmnPQQRn6yKRPKQS9Kz1m8lBnOra6EHU_59tIa2A6qLb2IyNeJ4a1PKm1dvxA-iExHajB-yrBQMGa3FpKrooMoc8eF8SAKMQmTGGMSS891XmbMmATL0GL6H4cFCga2R9IlAeeH8CXEflBoIYxXbMre8eK9BcmUX3jcMDD_yabEybmpiV7DMINlR87-2s0lrkXVCQXbzwppm47gBpNQfIad5tnK_rs3LNR5Dil7Oy4XFV58sn-r0jNQUtc2CijkB83FeINB35SMt4MTBCYmW2a36hEYjpjpxLTJXUIVQuo9iLtrF-skjVQHvva_DPrJSkgHNHZxpPVaIB_uWB7uCp_8yze9xxxNm00 "LAYOUT_TOP_DOWN Sample")

Using `LAYOUT_LEFT_RIGHT`

```csharp
@startuml LAYOUT_LEFT_RIGHT Sample
!includeurl https://raw.githubusercontent.com/treasure33/C4-PlantUML/master/C4_Container.puml

LAYOUT_LEFT_RIGHT

Person(admin, "Administrator")
System_Boundary(c1, 'Sample') {
    Container(web_app, "Web Application", "C#, ASP.NET Core 2.1 MVC", "Allows users to compare multiple Twitter timelines")
}
System(twitter, "Twitter")

Rel(admin, web_app, "Uses", "HTTPS")
Rel(web_app, twitter, "Gets tweets from", "HTTPS")
@enduml
```

![LAYOUT_LEFT_RIGHT Sample](http://www.plantuml.com/plantuml/png/PKzFxz904BtlfnZny2i9ja4yUQ8s22QW3IqQJytIZhB9_jdipgOXnk_kD22Ok9V9pdlp_gmZoK39QDYNtx-Sscw_-TXsnq_RNGkDD5wZUALihzE0AMYu4FdulYY27FEVYYxfd2A6tbb2ItdlJ441PKm1LwkYUlUcrjBIwR0lZ8o4WLTTnMIfB8RSiwqG__aAKME8pcPoCCekO5PEKqKAaboOpKLpPItJVN393Z9SitwvW9TRs9Sv_1B0x-6IZNZkfFUiymtFK7glLIz9EJlZLVLw0MLJvvytBPy4XBVv4WvVgmahjNPZXAbW17B0xRnaYacQ57j1EoeY343Ae6QloDb-tzDbT0DPvqvZK1nH_strZ7MAVCbprxPrmwo9z42VCbkao5-Sne_WpBydQxH3CleF "LAYOUT_LEFT_RIGHT Sample")

## LAYOUT_WITH_LEGEND

Colors can help to add additional information or simply to make the diagram more aesthetically pleasing.
It can also help to save some space.

All of that is the reason, C4-PlantUML uses colors and prefer also to enable a layout without `<<stereotypes>>` and with a legend.
This can be enabled with `LAYOUT_WITH_LEGEND()`.

```csharp
@startuml LAYOUT_WITH_LEGEND Sample
!includeurl https://raw.githubusercontent.com/treasure33/C4-PlantUML/master/C4_Container.puml

LAYOUT_WITH_LEGEND()

Person(admin, "Administrator")
System_Boundary(c1, 'Sample') {
    Container(web_app, "Web Application", "C#, ASP.NET Core 2.1 MVC", "Allows users to compare multiple Twitter timelines")
}
System(twitter, "Twitter")

Rel(admin, web_app, "Uses", "HTTPS")
Rel(web_app, twitter, "Gets tweets from", "HTTPS")
@enduml
```

![LAYOUT_WITH_LEGEND Sample](http://www.plantuml.com/plantuml/png/PL1Fxz904BtlfnZny2i9ja4yUQ9M0YQ0ZIqIJytIZhB9_jdipgOXnk_kDA2OsCkaC-_FUxkE90Cbes5VVljyQhlpftRNxJVRpV4ZDD9uZUALihrE0wQWuKhau_kY27BCVoYwfakA67fd2ItblJC51PGn1LojYkhTcrfBIwV3lZ0o4WPUTHM3fR8OSi--GlnldCs5g354PpCv66KNC2kdgI85IIxCvgAviPpfFhXa1nbkMRzSmCizxyiSVWhWxwzHDkAbazwppXalK7glLIz9EJlZLVLw0MLJvyTDovI0y3PVmk5hDTrAhTqOOUeOWHnmGIyPOf8cnLxGZegu5v0ogDahShPVZtGPtO-iyu3nKNn1_QVLCzOfCfFdhcthXb4CUeP-ocoH8l_YDBu7P_wbhD4E_9w_0G00 "LAYOUT_WITH_LEGEND Sample")

## LAYOUT_AS_SKETCH

C4-PlantUML can be especially helpful during up-front design sessions.
One thing which is often ignored is the fact, that these software architecture sketches are just sketches.

Without any proof

* if they are technically possible
* if they can fullfil all requirements
* if they keep what they promise

More often these sketches are used by many people as facts and are manifested into their documentations.
With `LAYOUT_AS_SKETCH()` you can make a difference.

```csharp
@startuml LAYOUT_AS_SKETCH Sample
!includeurl https://raw.githubusercontent.com/treasure33/C4-PlantUML/master/C4_Container.puml

LAYOUT_AS_SKETCH()

Person(admin, "Administrator")
System_Boundary(c1, 'Sample') {
    Container(web_app, "Web Application", "C#, ASP.NET Core 2.1 MVC", "Allows users to compare multiple Twitter timelines")
}
System(twitter, "Twitter")

Rel(admin, web_app, "Uses", "HTTPS")
Rel(web_app, twitter, "Gets tweets from", "HTTPS")
@enduml
```

![LAYOUT_AS_SKETCH Sample](http://www.plantuml.com/plantuml/png/NKzDYzim4BthLqpJGnn8RTBqr5DS4nfeqfhQQUd9AFQq4UX3I2DCAFlVTqoooRAw39htvdri8ib0oMZObtz-7DkkRBhcsxQjTj18upMATyhsEWsOWeOpaO-VYoB8CV-dw9nEAMBedIMqbFVE51HGnXHmlIwgJnzgBIqT3_l2o4WOUDLLJ9RAOiWzkmhnrZPR255ZYCvcSZ3ABc5MJbD52f9Sc2r4Ss4nqtrnoGuoNB9-jOJvDUry0Vy5yBlRP2EUEkazw_p64vJUQzLBKixEU5MzNqBPrFdtRSid0U5ZleB3hsh2IgtT665g684SS3qlcMAI9iLUq8wA20EGCgZPAtAsfrkwZAuWwzne38gVg5zQFM8T8r_otBLjtJ1h8jtHXynNfCXVdCRVuCphamtQ8Hdz3000 "LAYOUT_AS_SKETCH Sample")
