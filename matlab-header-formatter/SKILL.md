---
name: matlab-header-formatter
description: "Use this skill whenever you need to write, generate, or format MATLAB file headers — for class definitions (.m classdef files), class methods, or standalone functions. Triggers include: 'add a header to this MATLAB file', 'format the header', 'write a MATLAB function header', 'document this class', 'add MATLAB documentation', or any time the user provides MATLAB code and asks for documentation, headers, or comments to be added. Always use this skill when producing any MATLAB header output — do not invent your own header format."
---

# MATLAB Header Skill

Generate correctly formatted MATLAB headers for three file types: **classes**, **class methods**, and **standalone functions**.

---

## Logo Block

The logo block is used in class and standalone function headers (NOT method headers). Copy it exactly — spacing and characters are precise:

```
%                 .:. ##*.                        
%                ::::: ##### ++                   
%               .:::::: *###.:### +*-             
%             ##+ .::::: *### ##* ###: ##*        
%           -#####*  :::: +## +#= ##..###*        
%          -*########  ::: -#: # +# -##+ :###     
%         ##*:  =######- :: -# # # =#+ =#####     
%       =########*:  :*##=         . +##=.  -     
%      *###############+               ######     
%                                                 
%    ####################+           -*######     
%   :###############=  :=#+         :#*=   *#     
%    =########*-  .*####- *# :   : *#  *####=     
%      ###.  =*#######  ### ** #.+# +##: *###     
%       .*#########* :###* ##..#+ ## -###= =#     
%        :#######* =####* ### *## ### :####*      
%          ####: *#####= #### ### +###..#####     
%           =. #######- #### :###* ####: ###.     
%             #######: ##### *#### *####- =       
%              ##### :###### ##### +*-            
%               +## -###### -##+                  
%                  =#####+.                       
```

---

## 1. Class Header

Used at the top of a `classdef` file.

**Structure:** Logo block → metadata block → documentation block.

```matlab
%                 .:. ##*.                        
%                ::::: ##### ++                   
%               .:::::: *###.:### +*-             
%             ##+ .::::: *### ##* ###: ##*        
%           -#####*  :::: +## +#= ##..###*        
%          -*########  ::: -#: # +# -##+ :###     
%         ##*:  =######- :: -# # # =#+ =#####     
%       =########*:  :*##=         . +##=.  -     
%      *###############+               ######     
%                                                 
%    ####################+           -*######     
%   :###############=  :=#+         :#*=   *#     
%    =########*-  .*####- *# :   : *#  *####=     
%      ###.  =*#######  ### ** #.+# +##: *###     
%       .*#########* :###* ##..#+ ## -###= =#     
%        :#######* =####* ### *## ### :####*      
%          ####: *#####= #### ### +###..#####     
%           =. #######- #### :###* ####: ###.     
%             #######: ##### *#### *####- =       
%              ##### :###### ##### +*-            
%               +## -###### -##+                  
%                  =#####+.                       
%                                                 
%  Class Name:      <ClassName>.m
%  Created by:      <Author Name>
%  Modified by:     <Author Name>
%  Last Modified:   <YYYY-MM-DD>
%
% <CLASSNAME> <one-line class purpose>.
%
%   Description:
%       <Short paragraph about what this class represents/controls.>
%
%   Constructor:
%       OBJ = <CLASSNAME>(<args>)
%
%   Properties:
%       <Prop1>            <description>
%       <Prop2>            <description>
%
%   Methods:
%       <method1>          <description>
%       <method2>          <description>
%
%   Example:
%       OBJ = <CLASSNAME>(<args>);
%       OBJ.<method1>(<args>);
%
%   Notes:
%       - <constraint, assumption, or dependency>
%       - <units, calibration source, or side effects>
```

**Filling it in:**
- `<ClassName>` — the exact class name, preserving case (e.g., `MotorController`)
- `<CLASSNAME>` — uppercase version for the H1 line and constructor (e.g., `MOTORCONTROLLER`)
- Metadata fields: fill from context or leave as placeholders if unknown
- List all public properties and public/protected methods in their respective sections
- If the class has no output args, omit the `<OUT> =` prefix from the constructor line
- Omit any section (Properties, Methods, Example, Notes) only if it truly has no content

---

## 2. Class Method Header

Used inside a `methods` block, immediately before the `function` keyword. **No logo block.**

```matlab
% <FUNCTIONNAME> <one-line purpose statement>.
% <OUT> = <FUNCTIONNAME>(<required args>) <required usage description>.
%
% <OUT> = <FUNCTIONNAME>(<optional args>) <optional usage description>.
%
% Inputs:
% <ARG1> <description>.
% <ARG2> <description>.
% <ARG3> <description>.
%
% Output:
% <OUT> <description>.
%
% Notes:
% - <note 1>.
% - <note 2>.
% - <warning/assumption>.
```

**Filling it in:**
- `<FUNCTIONNAME>` — uppercase function name (e.g., `CONNECT`, `READDATA`)
- H1 line: one-sentence summary ending with a period
- Usage lines: one line per calling signature (required args, then optional/name-value variants)
- If the function has no output, omit the `<OUT> =` prefix from all usage lines and the Output section
- If there is only one calling signature, omit the second usage line
- Omit Inputs, Output, or Notes sections only if they are empty
- No blank line between the H1 line and the first usage line; blank line before each new section

---

## 3. Standalone Function Header

Used at the top of a standalone `.m` function file (not inside a class). **Includes logo block**, followed immediately by the function documentation (no metadata block).

```matlab
%                 .:. ##*.                        
%                ::::: ##### ++                   
%               .:::::: *###.:### +*-             
%             ##+ .::::: *### ##* ###: ##*        
%           -#####*  :::: +## +#= ##..###*        
%          -*########  ::: -#: # +# -##+ :###     
%         ##*:  =######- :: -# # # =#+ =#####     
%       =########*:  :*##=         . +##=.  -     
%      *###############+               ######     
%                                                 
%    ####################+           -*######     
%   :###############=  :=#+         :#*=   *#     
%    =########*-  .*####- *# :   : *#  *####=     
%      ###.  =*#######  ### ** #.+# +##: *###     
%       .*#########* :###* ##..#+ ## -###= =#     
%        :#######* =####* ### *## ### :####*      
%          ####: *#####= #### ### +###..#####     
%           =. #######- #### :###* ####: ###.     
%             #######: ##### *#### *####- =       
%              ##### :###### ##### +*-            
%               +## -###### -##+                  
%                  =#####+.                       
%        
% <FUNCTIONNAME> <one-line purpose statement>.
% <OUT> = <FUNCTIONNAME>(<required args>) <required usage description>.
%
% <OUT> = <FUNCTIONNAME>(<optional args>) <optional usage description>.
%
% Inputs:
% <ARG1> <description>.
% <ARG2> <description>.
% <ARG3> <description>.
%
% Output:
% <OUT> <description>.
%
% Notes:
% - <note 1>.
% - <note 2>.
% - <warning/assumption>.
```

**Filling it in:** Same rules as Class Method Header above. The only difference is the logo block above and the `%        ` spacer line between the logo and the H1 line.

---

## Decision Tree

```
Is this a classdef file?
├── YES → Class Header (logo + metadata + docs)
└── NO → Is this inside a methods block?
          ├── YES → Class Method Header (docs only, no logo)
          └── NO → Standalone Function Header (logo + docs)
```

---

## Common Rules Across All Types

- All comment lines start with `%`
- `<FUNCTIONNAME>` / `<CLASSNAME>` in usage/H1 lines are always **UPPERCASE**
- In the Properties and Methods sections of a class header, align descriptions using spaces (not tabs) so they form a clean column
- Never add extra blank lines inside the logo block
- Preserve all trailing spaces in the logo block lines exactly as shown
- If you are given actual code to document, extract real arg names, return values, properties, and method names — do not leave placeholder text where real information is available
