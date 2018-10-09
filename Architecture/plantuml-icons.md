# PlantUML icons

* [PlantUML Office](https://github.com/Roemer/plantuml-office)
* [Cloudinsight PlantUML sprites](https://github.com/rabelenda/cicon-plantuml-sprites)
* [Open Iconic](https://useiconic.com/open/)
* [Material Design](https://github.com/Templarian/MaterialDesign)
* [AWS PlantUML](https://github.com/milo-minderbinder/AWS-PlantUML)


### Examples

Default (Open Iconic)
```
@startuml
listopeniconic
@enduml
```

Devicons / Font-awesome
```
@startuml
 
' Include common to use icon macros.
!include <devicons/common>
' Include icon from Devicons.
!include <devicons/github>
' Include icon from Font Awesome icons.
!include <font-awesome/gitlab>
 
' Use macros from common library.
' First argument is alias, second label.
DEV_GITHUB(github, 'Github')
FA_GITLAB(gitlab, 'Gitlab')
 
' Use ~ to escape #
github -> gitlab : ~#movingtogitlab
 
@enduml
```