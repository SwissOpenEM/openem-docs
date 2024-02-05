# Key 
**Core Team**: funded by OpenEM
*Active Participant*: Co-authors and active collaborators
Participant: Line managers and passive collaborators

# PSI
```plantuml
@startwbs 
<style> 
node {
    HorizontalAlignment center
}
wbsDiagram {
  .newpos {
      FontColor red
      FontStyle bold
  }
}
</style>

+ PSI
++ Scientific Computing, Theory and Data
+++: Science IT Infrastructure and Services
----
Alun Ashton;
++++_ Leo Sala
+++++_ //Carlo Minotti//
+++++_ **Spencer Bliven**
++ Biology and Chemistry
+++_  //Gebhard Schertler//
+++_  //Gregor Cicchetti//
+++ Laboratory of Biomolecular Research
++++_ //Volodymyr Korkhov//
+++ Laboratory of Nanoscale Biology
++++: Electron Microscopy Facility
----
//Elisabeth Müller//;
+++++_ Emiliya Poghosyan

legend
Key
----
**Core Team**: funded by OpenEM
//Active Participant//: Co-authors and active collaborators
Participant: Line managers and passive collaborators
endlegend
@endwbs
```

# EMPA
```plantuml
@startwbs
+ EMPA
++ Advanced Materials and Surfaces
+++ Electron Microscopy Center
++++_ //Rolf Erni//
++++_ //Debora Keller//
++ Corporate Services
+++: Scientific IT
----
Eleni Pratsini;
++++_ **Despina Adamopoulou**
'++++_ Simone Baffelli
'++++_ Edoardo Baldi
@endwbs
```
[Ref](https://www.empa.ch/documents/20659/66489/Organigramm+English/81354988-9bd6-4b3c-984c-7cd5785f298e)
- Is Debora still involved?
# EPFL
```plantuml
@startwbs
<style>
wbsDiagram {

  .newpos {
      FontColor red
      FontStyle bold
  }
}
</style>

+ EPFL
++ School of Basic Sciences
+++ Institute of Physics
++++: Laboratory of Biological Electron Microscopy
----
//Henning Stahlberg//;
++ Centres and platforms
+++: CIME
----
//Marco Cantoni//;
+++: Dubochet Centre for Imaging
----
//Henning Stahlberg//;
++++_ Alexander Myasnikov
++++_ Sofya Laskina <<newpos>>
++ School of Engineering
+++ Institute of Bioengineering
++++: Laboratory of Nanoscale Biology
----
//Aleksandra Radenovic//;
@endwbs
```
# UNIL
```plantuml
@startwbs
+ UNIL
++ Biology and Medicine
+++: Electron Microscopy Facility
----
//Christel Genoud//;
@endwbs
```
# ETHZ
```plantuml
@startwbs
<style> 
wbsDiagram {
  .newpos {
      FontColor red
      FontStyle bold
  }
}
</style>

+ ETHZ
++: ScopeM
----
//Nicolas Blanc// (Managing Director)
//Christophe Copéret// (SC Chair);
+++_ //Christophe Briand//
+++_ //Miroslav Peterek//
+++_ //Bilal Qureshi//
+++_ //Andrzej Rzepiela//
++: Cryo-EM Knowledge Hub
----
//Daniel Böhringer//;
++ D-BIOL
+++_ //Vladimir Korkhov//
++ IT-Services
+++ Scientific IT Services
' ++++_ Sergio Maffioletti
++++_ Matthew Baker
+++++_ Philipp Wissmann

legend
Key
----
**Core Team**: funded by OpenEM
//Active Participant//: Co-authors and active collaborators
Participant: Line managers and passive collaborators
endlegend
@endwbs
```
- [X] Checked by Andrzej

# UNIBAS
```plantuml-svg
@startwbs
<style>
wbsDiagram {
  .newpos {
      FontColor red
      FontStyle bold
  }
}
</style>


+ UNIBAS
++ BioZentrum
+++: BioEM
----
//Mohamed Chami//;
+++_ //Timm Maier//
++++_ **Yves Tittes** 
++ sciCORE
+++_ //TBD//
@endwbs
```


# UNIGE
```plantuml
@startwbs
<style>
wbsDiagram {
  .newpos {
      FontColor red
      FontStyle bold
  }
    .matrix {
      LineColor #ccc;
      ArrowHeadColor none;
    }
}
</style>
+ UNIGE
++ Faculty of Science
+++ Section of Biology
++++: IT Service
----
//Thomas Pedretti//;
++++: Molecular and Cellular Biology
----
//Orsolya Barabas//;
+++++(RL)_ //Robbie Loewith//*
+++++_ //Andreas Boland//
+++++_ //Paul Guichard//

+++++(AH)_ //Andrew Howe//*
++++++(New)_ Attila Nacsa*
++++ Bioimaging Center
+++++(CB)_ Christoph Bauer*

++(DCI) DCI-Geneva
+++(Cryo) CryoGENic

DCI -> RL <<matrix>>
Cryo -> AH <<matrix>>
Cryo -> CB <<matrix>>
Cryo -> New <<matrix>>

legend
Key
----
**Core Team**: funded by OpenEM
//Active Participant//: Co-authors and active collaborators
Participant: Line managers and passive collaborators
 * DCI-Geneva member
endlegend
@endwbs
```

# UNIBE
```plantuml
@startwbs
<style> 
wbsDiagram {
  .newpos {
      FontColor red
      FontStyle bold
  }
}
</style> 
+ UNIBE
++ Institute of Anatomy
+++: Microscopic Anatomy and Structural Biology
----
//Benoît Zuber//;
++++_ David Kalbermatter
@endwbs
```




