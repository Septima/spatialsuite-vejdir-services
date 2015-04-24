##Septima module: vejman_services

###Installation

Unzip the file to /config/modules/thirdparty/septima

Add the module to modules_xxx.xml

<module name="vejdir_services" dir="thirdparty/septima/spatialsuite-vejdir-services" permissionlevel="public"/>

Insert this into your profile themegroups element:

```xml

[if: ModuleDefined("vejdir_services") ]
<include src="[module:vejdir_services.dir]/profiles/profile.xml" nodes="/profile/themegroups/*" mustexist="false"/>
[endif]

```

Insert this into your profile themes element to get all themes in the profile:

```xml
[if: ModuleDefined("vejdir_services") ]
<include src="[module:vejdir_services.dir]/profiles/profile.xml" nodes="/profile/themes/*" mustexist="false"/>
[endif]
```

Insert this into your profile themes element to get individual (theme-vd_admission) themes in the profile:

```xml
[if: ModuleDefined("vejdir_services") ]
<include src="[module:vejdir_services.dir]/profiles/profile.xml" nodes="//profile/themes/theme[@name='theme-vd_admission']" mustexist="false"/>
[endif]
```

Insert this into your targetsetfile:

```xml

[if: ModuleDefined("vejman") ]
<include src="[module:vejdir_services.dir]/queries/targetset.xml" nodes="/targetsets/targetset/*" mustexist="true"/>
[endif]

```
