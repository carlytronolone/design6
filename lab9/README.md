# Lab 9 - YANG
## Files for Lab 9 will be stored here
# Procedure
## First, I installed pyang and PlantUML:
```
carly@MSI MINGW32 ~
$ pip install pyang plantuml
Collecting pyang
  Downloading pyang-2.5.3-py2.py3-none-any.whl (592 kB)
     -------------------------------------- 592.9/592.9 kB 9.2 MB/s eta 0:00:00
Collecting plantuml
  Downloading plantuml-0.3.0-py3-none-any.whl (5.8 kB)
Collecting lxml
  Downloading lxml-4.9.2-cp311-cp311-win_amd64.whl (3.8 MB)
     ---------------------------------------- 3.8/3.8 MB 6.0 MB/s eta 0:00:00
Collecting httplib2
  Downloading httplib2-0.22.0-py3-none-any.whl (96 kB)
     ---------------------------------------- 96.9/96.9 kB 5.4 MB/s eta 0:00:00
Collecting pyparsing!=3.0.0,!=3.0.1,!=3.0.2,!=3.0.3,<4,>=2.4.2
  Downloading pyparsing-3.0.9-py3-none-any.whl (98 kB)
     ---------------------------------------- 98.3/98.3 kB 5.5 MB/s eta 0:00:00
Installing collected packages: pyparsing, lxml, pyang, httplib2, plantuml
Successfully installed httplib2-0.22.0 lxml-4.9.2 plantuml-0.3.0 pyang-2.5.3 pyparsing-3.0.9

[notice] A new release of pip available: 22.3 -> 23.1.2
[notice] To update, run: python.exe -m pip install --upgrade pip
```
## Given commands:
```
$ mkdir ~/demo
$ cp ~/iot/lesson9/intrusiondetection.yang ~/demo
$ cd ~/demo
$ cat intrusiondetection.yang
$ pyang -f yin -o intrusiondetection.yin intrusiondetection.yang
$ cat intrusiondetection.yin
$ pyang -f uml -o intrusiondetection.uml intrusiondetection.yang --uml-no=stereotypes,annotation,typedef
$ cat intrusiondetection.uml
$ python3 -m plantuml intrusiondetection.uml
```

# Results:

## cat intrusiondetection.yang
```
carly@MSI MINGW32 ~/demo
$ cat intrusiondetection.yang
module intrusiondetection {

 namespace "http://netconfcentral.org/ns/intrusiondetection";

 prefix "intrusion";

 description
  "YANG module for Intrusion Detection IoT system";

 revision 2014-07-15 {
  description "Intrusion Detection System";
 }

 grouping room {
  leaf doorsensorID {
   type string;
   description
    "ID of door sensor in the room";
  }
  leaf motionsensorID {
   type string;
   description
    "ID of motion sensor in the room";
  }
 }

 container intrusiondetection {
  presence
   "Indicates the service is available";

  description
   "Top-level container for all system objects.";

  leaf systemID {
   type string;
   config false;
   mandatory true;
   description
   "ID of the system";
  }

  leaf systemLocation {
   type string;
   config false;
   mandatory true;
   description
   "The location of the system";
  }

  leaf systemStatus {
   type enumeration {
    enum up {
    value 1;
    description
     "This is powered up";
    }
    enum down {
    value 2;
    description
     "This is powered down";
    }
    enum armed {
    value 3;
    description
     "This is armed";
    }
    enum disarmed {
    value 4;
    description
     "This is disarmed";
    }
   }
   config false;
   mandatory true;
   description
   "This variable indicates the current state of
    the system.";
  }
    container sensors {
   uses room;
   config false;
  }
 }

 rpc arm-system {
  description
   "Arm the system";
 }

 rpc disarm-system {
  description
   "Disarm the system";
 }

 notification systemArmed {
  description
   "Indicates that system has been armed.";

  leaf armStatus {
   description
    "Indicates the system arming status";

   type enumeration {
    enum armed {
    description
     "The system was armed.";
    }

    enum disarmed {
    description
     "The system was disarmed.";
    }

    enum error {
    description
     "The system is broken.";
    }
   }
  }
 }
}
```

## cat intrusiondetection.yin
```
carly@MSI MINGW32 ~/demo
$ cat intrusiondetection.yin
<?xml version="1.0" encoding="UTF-8"?>
<module name="intrusiondetection"
        xmlns="urn:ietf:params:xml:ns:yang:yin:1"
        xmlns:intrusion="http://netconfcentral.org/ns/intrusiondetection">
  <namespace uri="http://netconfcentral.org/ns/intrusiondetection"/>
  <prefix value="intrusion"/>
  <description>
    <text>YANG module for Intrusion Detection IoT system</text>
  </description>
  <revision date="2014-07-15">
    <description>
      <text>Intrusion Detection System</text>
    </description>
  </revision>
  <grouping name="room">
    <leaf name="doorsensorID">
      <type name="string"/>
      <description>
        <text>ID of door sensor in the room</text>
      </description>
    </leaf>
    <leaf name="motionsensorID">
      <type name="string"/>
      <description>
        <text>ID of motion sensor in the room</text>
      </description>
    </leaf>
  </grouping>
  <container name="intrusiondetection">
    <presence value="Indicates the service is available"/>
    <description>
      <text>Top-level container for all system objects.</text>
    </description>
    <leaf name="systemID">
      <type name="string"/>
      <config value="false"/>
      <mandatory value="true"/>
      <description>
        <text>ID of the system</text>
      </description>
    </leaf>
    <leaf name="systemLocation">
      <type name="string"/>
      <config value="false"/>
      <mandatory value="true"/>
      <description>
        <text>The location of the system</text>
      </description>
    </leaf>
    <leaf name="systemStatus">
      <type name="enumeration">
        <enum name="up">
          <value value="1"/>
          <description>
            <text>This is powered up</text>
          </description>
        </enum>
        <enum name="down">
          <value value="2"/>
          <description>
            <text>This is powered down</text>
          </description>
        </enum>
        <enum name="armed">
          <value value="3"/>
          <description>
            <text>This is armed</text>
          </description>
        </enum>
        <enum name="disarmed">
          <value value="4"/>
          <description>
            <text>This is disarmed</text>
          </description>
        </enum>
      </type>
      <config value="false"/>
      <mandatory value="true"/>
      <description>
        <text>This variable indicates the current state of
the system.</text>
      </description>
    </leaf>
    <container name="sensors">
      <uses name="room"/>
      <config value="false"/>
    </container>
  </container>
  <rpc name="arm-system">
    <description>
      <text>Arm the system</text>
    </description>
  </rpc>
  <rpc name="disarm-system">
    <description>
      <text>Disarm the system</text>
    </description>
  </rpc>
  <notification name="systemArmed">
    <description>
      <text>Indicates that system has been armed.</text>
    </description>
    <leaf name="armStatus">
      <description>
        <text>Indicates the system arming status</text>
      </description>
      <type name="enumeration">
        <enum name="armed">
          <description>
            <text>The system was armed.</text>
          </description>
        </enum>
        <enum name="disarmed">
          <description>
            <text>The system was disarmed.</text>
          </description>
        </enum>
        <enum name="error">
          <description>
            <text>The system is broken.</text>
          </description>
        </enum>
      </type>
    </leaf>
  </notification>
</module>
```

## cat intrusiondetection.uml
```carly@MSI MINGW32 ~/demo
$ cat intrusiondetection.uml
'Download plantuml from http://plantuml.sourceforge.net/
'Generate png with java -jar plantuml.jar <file>
'Output in img/<module>.png
'If Java spits out memory error increase heap size with java -Xmx1024m  -jar plantuml.jar <file>
@startuml img/intrusiondetection.png
hide empty fields
hide empty methods
hide <<case>> circle
hide <<augment>> circle
hide <<choice>> circle
hide <<leafref>> stereotype
hide <<leafref>> circle
hide stereotypes
page 1x1
Title intrusiondetection
package "intrusion:intrusiondetection" as intrusion_intrusiondetection {
class "intrusiondetection" as intrusiondetection << (M, #33CCFF) module>>
class "room" as intrusiondetection_I_room_grouping <<(G,Lime) grouping>>
intrusiondetection_I_room_grouping : doorsensorID : string
intrusiondetection_I_room_grouping : motionsensorID : string
class "intrusiondetection" as  intrusiondetection_I_intrusiondetection <<container>>
intrusiondetection *-- "0..1" intrusiondetection_I_intrusiondetection
intrusiondetection_I_intrusiondetection : systemID : string   {mandatory} {Config : false}
intrusiondetection_I_intrusiondetection : systemLocation : string   {mandatory} {Config : false}
intrusiondetection_I_intrusiondetection : systemStatus : enumeration : {up,down,armed,...}   {mandatory} {Config : false}
class "sensors" as  intrusiondetection_I_intrusiondetection_I_sensors <<container>>
intrusiondetection_I_intrusiondetection *-- "1" intrusiondetection_I_intrusiondetection_I_sensors
intrusiondetection_I_intrusiondetection_I_sensors : room {uses}
intrusiondetection : arm-system()
intrusiondetection : disarm-system()
class "systemArmed" as intrusiondetection_I_systemArmed << (N,#00D1B2) notification>>
intrusiondetection -- intrusiondetection_I_systemArmed : notification
intrusiondetection_I_systemArmed : armStatus : enumeration : {armed,disarmed,error,}
}

intrusiondetection_I_intrusiondetection_I_sensors --> intrusiondetection_I_room_grouping : uses
center footer
 <size:20> UML Generated : 2023-05-04 17:55 </size>
 endfooter
@enduml
```

## python -m plantuml intrusiondetection.uml
```
carly@MSI MINGW32 ~/demo
$ python -m plantuml intrusiondetection.uml
Traceback (most recent call last):
  File "<frozen runpy>", line 198, in _run_module_as_main
  File "<frozen runpy>", line 88, in _run_code
  File "C:\Python311\Lib\site-packages\plantuml.py", line 13, in <module>
    import six
ModuleNotFoundError: No module named 'six'
```
#### I am unable to run PlantUML to geneate intrisiondetection.png :((




