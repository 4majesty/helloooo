```xml
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE nta PUBLIC '-//Uppaal Team//DTD Flat System 1.1//EN' 'http://www.it.uu.se/research/group/darts/uppaal/flat-1_2.dtd'>
<nta>
   <declaration>// Place global declarations here.
clock x,y;</declaration>
   <template>
      <name x="5" y="5">A</name>
      <declaration>// Place local declarations here.</declaration>
      <location id="id0" x="34" y="-34">
         <name x="24" y="-68">S1</name>
         <label kind="invariant" x="24" y="-17">x&lt;=1</label>
      </location>
      <location id="id1" x="-170" y="-34">
         <name x="-180" y="-68">S0</name>
         <label kind="invariant" x="-180" y="-17">x&lt;=1</label>
      </location>
      <init ref="id1"/>
      <transition>
         <source ref="id0"/>
         <target ref="id1"/>
         <label kind="guard" x="-85" y="17">x==1</label>
         <label kind="assignment" x="-85" y="51">x=0</label>
         <nail x="-68" y="51"/>
      </transition>
      <transition>
         <source ref="id1"/>
         <target ref="id0"/>
         <label kind="guard" x="-93" y="-127">x==1</label>
         <label kind="assignment" x="-93" y="-102">x=0</label>
         <nail x="-76" y="-110"/>
      </transition>
   </template>
   <template>
      <name>S</name>
      <location id="id2" x="119" y="-8">
         <name x="109" y="-42">D</name>
         <label kind="invariant" x="109" y="9">y&lt;=4</label>
      </location>
      <location id="id3" x="17" y="-8">
         <name x="7" y="-42">C</name>
         <label kind="invariant" x="8" y="8">y&lt;=4</label>
      </location>
      <location id="id4" x="-85" y="-8">
         <name x="-95" y="-42">B</name>
         <label kind="invariant" x="-95" y="9">y&lt;=1</label>
      </location>
      <location id="id5" x="-178" y="-8">
         <name x="-188" y="-42">A</name>
         <label kind="invariant" x="-188" y="9">y&lt;=0</label>
         <committed/>
      </location>
      <init ref="id5"/>
      <transition>
         <source ref="id2"/>
         <target ref="id2"/>
         <label kind="guard" x="153" y="-25">y==4</label>
         <nail x="170" y="-59"/>
         <nail x="170" y="34"/>
      </transition>
      <transition>
         <source ref="id4"/>
         <target ref="id4"/>
         <label kind="guard" x="-109" y="-110">y==1</label>
         <label kind="assignment" x="-109" y="-76">y=0</label>
         <nail x="-127" y="-76"/>
         <nail x="-51" y="-76"/>
      </transition>
      <transition>
         <source ref="id3"/>
         <target ref="id2"/>
         <label kind="guard" x="34" y="-42">y==4</label>
      </transition>
      <transition>
         <source ref="id4"/>
         <target ref="id3"/>
         <label kind="guard" x="-59" y="-34">y==1</label>
         <label kind="assignment" x="-59" y="-8">y=0</label>
      </transition>
      <transition>
         <source ref="id5"/>
         <target ref="id4"/>
         <label kind="guard" x="-161" y="-34">y==0</label>
         <label kind="assignment" x="-153" y="-8">y=1</label>
      </transition>
   </template>
   <system>// Place template instantiations here.
//Process = Template();
// List one or more processes to be composed into a system.
system A,S;
    </system>
   <queries>
   </queries>
</nta>

 ```
