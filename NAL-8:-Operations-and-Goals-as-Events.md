---------------------------------------------------------------------------------------------

`//The goal is to make t001 opened.`
<br/>
<br/>
`<{t001} --> [opened]>!`
<br/>
<br/>
`//If the robot hold t002, then go to t001 and open t001, then t001 will be opened. `
<br/>
<br/>
`<(&/,<(*,SELF,{t002}) --> hold>,<(*,SELF,{t001}) --> at>,<(*,{t001}) --> ^open>) =/> <{t001} --> [opened]>>.`
<br/>
<br/>
`20`
<br/>
<br/>
`//outputMustContain('(&/,<(*,SELF,{t002}) --> hold>,<(*,SELF,{t001}) --> at>,(^open,{t001}))! %1.00;0.81%')`

---------------------------------------------------------------------------------------------

`//The goal is to hold t002, then arrive t001 and open t001`
<br/>
<br/>
`(&/,<(*,SELF,{t002}) --> hold>,<(*,SELF,{t001}) --> at>,(^open,{t001}))!`
<br/>
<br/>
`10`
<br/>
<br/>
`//The goal is to hold t002`
<br/>
<br/>
`//outputMustContain('<(*,SELF,{t002}) --> hold>! %1.00;0.81%')`

---------------------------------------------------------------------------------------------

`//The goal for the robot is to make t002 reachable and then pick it. `
<br/>
<br/>
`(&/,<(*,SELF,{t002}) --> reachable>,(^pick,{t002}))!`
<br/>
<br/>
`5`
<br/>
<br/>
`//The goal for the robot is to make t002 reachable. `
<br/>
<br/>
`//outputMustContain('<(*,SELF,{t002}) --> reachable>! %1.00;0.81%')`

---------------------------------------------------------------------------------------------

`//The goal for the robot is to make t002 reachable. `
<br/>
<br/>
`<(*,SELF,{t002}) --> reachable>! `
<br/>
<br/>
`//If item 1 is on item 2 and the robot is also at item 2 at the same time, the robot will be able to reach item 1. `
<br/>
<br/>
`<(&|,<(*,,#2) --> on>,<(*,SELF,#2) --> at>)=|><(*,SELF,) --> reachable>>.`
<br/>
<br/>
`10`
<br/>
<br/>
`//The goal is to make the robot at #1 and t002 is on #1 at the same time`
<br/>
<br/>
`//outputMustContain('(&|,<(*,SELF,#1) --> at>,<(*,{t002},#1) --> on>)! %1.00;0.81%')`

---------------------------------------------------------------------------------------------

`//t002 is on t003 now. `
<br/>
<br/>
`<(*,{t002},{t003}) --> on>. :|: `
<br/>
<br/>
`//The goal is to make t002 on #1 and #1 is at the robot at same time`
<br/>
<br/>
`(&|,<(*,{t002},#1) --> on>,<(*,#1,SELF) --> at>)! `
<br/>
<br/>
350
<br/>
<br/>
`//The goal maybe to make t003 at the robot`
<br/>
<br/>
`//outputMustContain('<(*,{t003},SELF) --> at>! %1.00;0.43%')`

---------------------------------------------------------------------------------------------

`//The goal for the robot is to arrive t003. `
<br/>
<br/>
`<(*,SELF,{t003}) --> at>!`
<br/>
<br/>
`//If go to somewhere, the robot will be at there.`
<br/>
<br/>
`<(^go-to,)=/><(*,SELF,) --> at>>.`
<br/>
<br/>
`100`
<br/>
<br/>
`//The goal is to go to t003.`
<br/>
<br/>
`//outputMustContain('(^go-to,{t003})! %1.00;0.81%')`

---------------------------------------------------------------------------------------------

`//Now the robot is going to t003. `
<br/>
<br/>
`<(*,{t003}) --> ^go-to>. :|: `
<br/>
<br/>
`//If go to somewhere, the robor will be at there.`
<br/>
<br/>
`<<(*,) --> ^go-to> =/> <(*,SELF,) --> at>>. `
<br/>
<br/>
`20`
<br/>
<br/>
`//The robot will be at t003. `
<br/>
<br/>
`//outputMustContain('<(*,SELF,{t003}) --> at>. :!5: %1.00;0.81%')`

---------------------------------------------------------------------------------------------

`//The robot was at t003. `
<br/>
<br/>
`<SELF --> (/,at,_,{t003})>. :\:`
<br/>
<br/>
`6`
<br/>
<br/>
`//The robot was at t003. `
<br/>
<br/>
`//outputMustContain('<{t003} --> (/,at,SELF,_)>. :!-5: %1.00;0.90%')`

---------------------------------------------------------------------------------------------

`//t002 is on t003 now.`
<br/>
<br/>
`<(*,{t002},{t003}) --> on>. :|:`
<br/>
<br/>
`6`
<br/>
<br/>
`//t002 is on t003 now.`
<br/>
<br/>
`//outputMustContain('<{t003} --> (/,on,{t002},_)>. :!0: %1.00;0.90%')`

---------------------------------------------------------------------------------------------

`//The robot was at t003.`
<br/>
<br/>
`<{t003} --> (/,at,SELF,_)>. :\:`
<br/>
<br/>
`//t002 was on the t003. `
<br/>
<br/>
`<{t003} --> (/,on,{t002},_)>. :\:`
<br/>
<br/>
`33`
<br/>
<br/>
`//If the robot was at something, t002 was also on it. `
<br/>
<br/>
`//outputMustContain('(&&,<#1 --> (/,at,SELF,_)>,<#1 --> (/,on,{t002},_)>). :!-5: %1.00;0.81%')`

---------------------------------------------------------------------------------------------

`//t002 was on something and the robot was also at it at the same time.`
<br/>
<br/>
`(&|,<#1 --> (/,on,{t002},_)>,<#1 --> (/,at,SELF,_)>). :\:`
<br/>
<br/>
`8`
<br/>
<br/>
`//t002 was on something and the robot was also at it at the same time.`
<br/>
<br/>
`//outputMustContain('(&|,<#1 --> (/,on,{t002},_)>,<(*,SELF,#1) --> at>). :!-5: %1.00;0.90%')`

---------------------------------------------------------------------------------------------

`//t002 is on something, and the robot is also at it at the same time. `
<br/>
<br/>
`(&|,<(*,{t002},#1) --> on>,<(*,SELF,#1) --> at>). :|: `
<br/>
<br/>
`//If item 1 is on item 2 and the robot is also at item 2 at the same time, the robot will be able to reach item 1. `
<br/>
<br/>
`<(&|,<(*,,) --> on>,<(*,SELF,) --> at>) =|> <(*,SELF,) --> reachable>>.`
<br/>
<br/>
`260`
<br/>
<br/>
`//The robot is able to reach t002. `
<br/>
<br/>
`//outputMustContain('<(*,SELF,{t002}) --> reachable>. :!0: %1.00;0.81%')`

---------------------------------------------------------------------------------------------

`//The robot is able to reach t002. `
<br/>
<br/>
`<(*,SELF,{t002}) --> reachable>. :|: `
<br/>
<br/>
`//The goal for the robot is to make t002 reachable and then pick it. `
<br/>
<br/>
`(&/,<(*,SELF,{t002}) --> reachable>,(^pick,{t002}))! `
<br/>
<br/>
`45`
<br/>
<br/>
`//The goal maybe to pick t002. `
<br/>
<br/>
`//outputMustContain('(^pick,{t002})! %1.00;0.43%')`

---------------------------------------------------------------------------------------------

`//The robot is able to reach t002. `
<br/>
<br/>
`<(*,SELF,{t002}) --> reachable>. :|:`
<br/>
<br/>
`//If the robot reach t002 and pick it, the robot will hold t002.`
<br/>
<br/>
`<(&/,<(*,SELF,{t002}) --> reachable>,(^pick,{t002}))=/><(*,SELF,{t002}) --> hold>>.`
<br/>
<br/>
`1`
<br/>
<br/>
`//If the robot pick t002, it will hold t002. `
<br/>
<br/>
`//outputMustContain('<(^pick,{t002}) =/> <(*,SELF,{t002}) --> hold>>. :!0: %1.00;0.81%')`

---------------------------------------------------------------------------------------------

`//t002 is picked. `
<br/>
<br/>
`(^pick,{t002}). :\:`
<br/>
<br/>
`//If the robot pick t002, it will hold t002.`
<br/>
<br/>
`<(^pick,{t002})=/><(*,SELF,{t002}) --> hold>>. :\:`
<br/>
<br/>
`20`
<br/>
<br/>
`//The robot is holding t002. `
<br/>
<br/>
`//outputMustContain('<(*,SELF,{t002}) --> hold>. :!0: %1.00;0.81%')`

---------------------------------------------------------------------------------------------

`//The robot is holding t002. `
<br/>
<br/>
`<(*,SELF,{t002}) --> hold>. :|:  `
<br/>
<br/>
`//The robot should hold t002, then arrive t001 and open t001.`
<br/>
<br/>
`(&/,<(*,SELF,{t002}) --> hold>,+100,<(*,SELF,{t001}) --> at>,+100,(^open,{SELF},{t001}))! `
<br/>
<br/>
`30`
<br/>
<br/>
`//The robot should arrive t001 then open t001. `
<br/>
<br/>
`//outputMustContain('(&/,<(*,SELF,{t001}) --> at>,+100,(^open,{SELF},{t001}))! :!100: %1.00;0.73%')`

---------------------------------------------------------------------------------------------

`//If the robot hold t002, then arrive t001 and open it, t001 will be opened. `
<br/>
<br/>
`<(&/,<(*,SELF,{t002}) --> hold>,<(*,SELF,{t001}) --> at>,(^open,{SELF},{t001})) =/> <{t001} --> [opened]>>. %1.00;0.90%`
<br/>
<br/>
`//The robot is holding t002 now.`
<br/>
<br/>
`<(*,SELF,{t002}) --> hold>. :|:`
<br/>
<br/>
`200`
<br/>
<br/>
`//If the robot arrive t001 and open it, t001 may be opened. `
<br/>
<br/>
`//outputMustContain('<(&/,<(*,SELF,{t001}) --> at>,(^open,{SELF},{t001})) =/> <{t001} --> [opened]>>. %1.00;0.43%')`

---------------------------------------------------------------------------------------------

`//The goal for the robot is to reach t001 and then open t001. `
<br/>
<br/>
`(&/,<(*,SELF,{t001}) --> at>,(^open,{t001}))! `
<br/>
<br/>
`13`
<br/>
<br/>
`//The goal for the robot is to reach t001. `
<br/>
<br/>
`//outputMustContain('<(*,SELF,{t001}) --> at>! %1.00;0.81%')`

---------------------------------------------------------------------------------------------

`//The goal is to reach t001. `
<br/>
<br/>
`<(*,SELF,{t001}) --> at>!`
<br/>
<br/>
`//If go to somewhere, the robot will be at there.`
<br/>
<br/>
`<(^go-to,)=/><(*,SELF,) --> at>>.`
<br/>
<br/>
`500`
<br/>
<br/>
`//The goal is to go to t001. `
<br/>
<br/>
`//outputMustContain('(^go-to,{t001})! %1.00;0.81%')`

---------------------------------------------------------------------------------------------

`//The robot went to t001. `
<br/>
<br/>
`(^go-to,{SELF},{t001}). :\: `
<br/>
<br/>
`//If go to somewhere, the robot will be at there.`
<br/>
<br/>
`<(^go-to,{SELF},)=/><(*,{SELF},) --> at>>. `
<br/>
<br/>
`41`
<br/>
<br/>
`//Was the robot at t001?`
<br/>
<br/>
`IN: <(*,{SELF},{t001}) --> at>? :\:`
<br/>
<br/>
`140`
<br/>
<br/>
`//The robot was at t001.`
<br/>
<br/>
`//outputMustContain('<(*,{SELF},{t001}) --> at>. :!0: %1.00;0.81%')`

---------------------------------------------------------------------------------------------

`//The robot is at t001 now. `
<br/>
<br/>
`<(*,SELF,{t001}) --> at>. :|: `
<br/>
<br/>
`//If the robot arrive t001 and open it, t001 will be opened. `
<br/>
<br/>
`<(&/,<(*,SELF,{t001}) --> at>,+100,(^open,{t001}))=/><{t001} --> [opened]>>. :|:`
<br/>
<br/>
`20`
<br/>
<br/>
`//If the robot open t001, t001 will be opened. `
<br/>
<br/>
`//outputMustContain('<(^open,{t001}) =/> <{t001} --> [opened]>>. :!100: %1.00;0.81%')`

---------------------------------------------------------------------------------------------

`//The robot is at t001 now.`
<br/>
<br/>
`<(*,SELF,{t001}) --> at>. :|:`
<br/>
<br/>
`//The goal is to arrive t001 and then open t001. `
<br/>
<br/>
`(&/,<(*,SELF,{t001}) --> at>,(^open,{SELF},{t001}))! `
<br/>
<br/>
`25`
<br/>
<br/>
`//The goal maybe to open t001.`
<br/>
<br/>
`//outputMustContain('(^open,{SELF},{t001})! %1.00;0.43%')`

---------------------------------------------------------------------------------------------

`//If the robot open t001, t001 will be opened.  `
<br/>
<br/>
`<(^open,{SELF},{t001})=/><{t001} --> [opened]>>. :|: `
<br/>
<br/>
`//The robot open t001. `
<br/>
<br/>
`(^open,{SELF},{t001}). :|:`
<br/>
<br/>
`1`
<br/>
<br/>
`//t001 is opened.`
<br/>
<br/>
`//outputMustContain('<{t001} --> [opened]>. :!5: %1.00;0.81%')`

---------------------------------------------------------------------------------------------

`//If the robot hold t002, then go to t001 and open it, t001 will be opened.`
<br/>
<br/>
`<(&/,<(*,Self,{t002}) --> hold>,(^go-to,{t001}),(^open,{t001})) =/> <{t001} --> [opened]>>.  `
<br/>
<br/>
`//If the robot is able to reach t002 and pick it, the robot will hold t002. `
<br/>
<br/>
`<(&/,<(*,Self,{t002}) --> reachable>,(^pick,{t002})) =/> <(*,Self,{t002}) --> hold>>.  `
<br/>
<br/>
`40`
<br/>
<br/>
`//If the robot is able to reach t002 and pick t002, then go to t001 and open t001, t001 will be opened.`
<br/>
<br/>
`//outputMustContain('<(&/,<(*,Self,{t002}) --> reachable>,(^pick,{t002}),(^go-to,{t001}),(^open,{t001})) =/> <{t001} --> [opened]>>. %1.00;0.81%')`

---------------------------------------------------------------------------------------------

`//If item 1 is on item 2 and the robot is at item 2 at the same time, item 1 is reachable for the robot. `
<br/>
<br/>
`<(&|,<(*,,) --> on>,<(*,Self,) --> at>) =|> <(*,Self,) --> reachable>>.`
<br/>
<br/>
`//t002 is on t003 now. `
<br/>
<br/>
`<(*,{t002},{t003}) --> on>. :|:`
<br/>
<br/>
`80`
<br/>
<br/>
`//If the robot is at t003, then t002 is reachable for the robot.`
<br/>
<br/>
`//outputMustContain('<<(*,Self,{t003}) --> at> =|> <(*,Self,{t002}) --> reachable>>. :!0: %1.00;0.81%')`

---------------------------------------------------------------------------------------------

`//If the robot is at t003 and pick t002, then go to t001 and open t001, t001 will be opened. `
<br/>
<br/>
`<(&/,<(*,Self,{t003}) --> at>,(^pick,{t002}),(^go-to,{t001}),(^open,{t001})) =/> <{t001} --> [opened]>>. :|: `
<br/>
<br/>
`//If go to somewhere, the robor will be at there.`
<br/>
<br/>
`<(^go-to,) =/> <(*,Self,) --> at>>.  `
<br/>
<br/>
`16`
<br/>
<br/>
`//If the robot goes to t003 and pick t002, then go to t001 and open t001, t001 may be opened.`
<br/>
<br/>
`//outputMustContain('<(&/,(^go-to,{t003}),(^pick,{t002}),(^go-to,{t001}),(^open,{t001})) =/> <{t001} --> [opened]>>. %1.00;0.43%')`

---------------------------------------------------------------------------------------------

`//The goal is to make t001 opened. `
<br/>
<br/>
`<{t001} --> [opened]>!  `
<br/>
<br/>
`//If the robot go to t003 and pick t002, then go to t001 and open t001, t001 will be opened.`
<br/>
<br/>
`<(&/,(^go-to,{t003}),(^pick,{t002}),(^go-to,{t001}),(^open,{t001})) =/> <{t001} --> [opened]>>. :|:`
<br/>
<br/>
`24`
<br/>
<br/>
`//The goal may be to go to t003 and pick t002, then go to t001 and open t001.`
<br/>
<br/>
`//outputMustContain('(&/,(^go-to,{t003}),(^pick,{t002}),(^go-to,{t001}),(^open,{t001}))! %1.00;0.43%')`

---------------------------------------------------------------------------------------------

`//The goal is to make t001 opened.`
<br/>
<br/>
`<{t001} --> [opened]>!  `
<br/>
<br/>
`//If the robot is at t001 and break t001, t001 will be opened.`
<br/>
<br/>
`<(&/,<(*,Self,{t001}) --> at>,(^break,{t001})) =/> <{t001} --> [opened]>>.`
<br/>
<br/>
`28`
<br/>
<br/>
`//The goal is to arrrive t001 and break t001.`
<br/>
<br/>
`//outputMustContain('(&/,<(*,Self,{t001}) --> at>,(^break,{t001}))! %1.00;0.81%')`

---------------------------------------------------------------------------------------------

`//The goal is to arrrive t001 and break t001.`
<br/>
<br/>
`(&/,<(*,Self,{t001}) --> at>,(^break,{t001}))! `
<br/>
<br/>
`//Now the robot is at t001. `
<br/>
<br/>
`<(*,Self,{t001}) --> at>. :|: `
<br/>
<br/>
`25`
<br/>
<br/>
`//The goal maybe to break t001.`
<br/>
<br/>
`//outputMustContain('(^break,{t001})! %1.00;0.43%')`

---------------------------------------------------------------------------------------------

`//If break something, it will be damaged. `
<br/>
<br/>
`<(^break,) =/> < --> [damaged]>>.`
<br/>
<br/>
`//The goal is to make t001 damaged. `
<br/>
<br/>
`<{t001} --> [damaged]>! `
<br/>
<br/>
`17`
<br/>
<br/>
`//The goal is to break t001.`
<br/>
<br/>
`//outputMustContain('(^break,{t001})! %1.00;0.81%')`

---------------------------------------------------------------------------------------------

`//The goal is not to break t001. `
<br/>
<br/>
`(^break,{t001})! %0.00;0.86% `
<br/>
<br/>
`1`
<br/>
<br/>
`//The goal is to break t001.`
<br/>
<br/>
`(^break,{t001})! %1.00;0.73% `
<br/>
<br/>
`1`
<br/>
<br/>
`//The goal may be not to break t001.`
<br/>
<br/>
`//outputMustContain('(^break,{t001})! %0.31;0.90%')`

---------------------------------------------------------------------------------------------

`//The goal may be not to break t001.`
<br/>
<br/>
`(^break,{t001})! %0.31;0.89% `
<br/>
<br/>
`1`
<br/>
<br/>
`//The goal is to break t001`
<br/>
<br/>
`(^break,{t001})! %1.00;0.95% `
<br/>
<br/>
`1`
<br/>
<br/>
`//The goal may be to break t001.`
<br/>
<br/>
`//outputMustContain('(^break,{t001})! %0.79;0.96%')`

---------------------------------------------------------------------------------------------

`//The robot is able to reach the key001 now. `
<br/>
<br/>
`<(*,Self,key001) --> reachable>. :|: `
<br/>
<br/>
`//If the robot is able to reach key001, and pick key001, the robot will hold key001. `
<br/>
<br/>
`<(&/,<(*,Self,key001) --> reachable>,(^pick,key001)) =/> <(*,Self,key001) --> hold>>.`
<br/>
<br/>
`1`
<br/>
<br/>
`//If the robot pick key001, it will hold key001. `
<br/>
<br/>
`//outputMustContain('<(^pick,key001) =/> <(*,Self,key001) --> hold>>. :!0: %1.00;0.81%')`

---------------------------------------------------------------------------------------------

`//If the robot pick key001, it will hold key001. `
<br/>
<br/>
`<(^pick,key001) =/> <(*,Self,key001) --> hold>>. :|:  `
<br/>
<br/>
`//The goal is to hold key001.`
<br/>
<br/>
`<(*,Self,key001) --> hold>!  `
<br/>
<br/>
`8`
<br/>
<br/>
`//The goal maybe to pick key001.`
<br/>
<br/>
`//outputMustContain('(^pick,key001)! %1.00;0.43%') `

---------------------------------------------------------------------------------------------

`//Key001 was picked. `
<br/>
<br/>
`(^pick,key001). :\: `
<br/>
<br/>
`//If the robot pick key001, it will hold key001. `
<br/>
<br/>
`<(^pick,key001) =/> <(*,Self,key001) --> hold>>.  `
<br/>
<br/>
`15`
<br/>
<br/>
`//The robot is holding key001.`
<br/>
<br/>
`//outputMustContain('<(*,Self,key001) --> hold>. :!0: %1.00;0.81%') `

---------------------------------------------------------------------------------------------

`//The robot is holding key001. `
<br/>
<br/>
`<(*,Self,key001) --> hold>. :|: %1.00;0.81% `
<br/>
<br/>
`1`
<br/>
<br/>
`//The robot is holding key001. `
`<(*,Self,key001) --> hold>. :|:`
<br/>
<br/>
5
<br/>
<br/>
`//The robot is holding key001. `
<br/>
<br/>
`//outputMustContain('<(*,Self,key001) --> hold>. :!1: %1.00;0.93%')` 

---------------------------------------------------------------------------------------------

`//The robot is not holding key001. `
<br/>
<br/>
`<(*,Self,key001) --> hold>. :|: %0% `
<br/>
<br/>
`5`
<br/>
<br/>
`//The robot is holding key001. `
<br/>
<br/>
`<(*,Self,key001) --> hold>. :|: %1.00;0.91% `
<br/>
<br/>
`5`
<br/>
<br/>
`//Is the robot holding key001?`
<br/>
<br/>
`<(*,Self,key001) --> hold>? :|: `
<br/>
<br/>
`50`
<br/>
<br/>
`//The robot may be holding key001.`
<br/>
<br/>
`//outputMustContain('<(*,Self,key001) --> hold>. :!5: %0.53;0.95%') `

---------------------------------------------------------------------------------------------

`//If pick key001, the robot will hold key001. `
<br/>
<br/>
`<(^pick,key001) =/> <(*,Self,key001) --> hold>>. :\: %1.00;0.90%`
<br/>
<br/>
`//If pick key001, the robot may hold key001. `
<br/>
<br/>
`<(^pick,key001) =/> <(*,Self,key001) --> hold>>. :\: %1.00;0.45% `
<br/>
<br/>
`35`
<br/>
<br/>
`//If pick key001, the robot will hold key001. `
<br/>
<br/>
`//outputMustContain('<(^pick,key001) =/> <(*,Self,key001) --> hold>>. :!-5: %1.00;0.91%')`

---------------------------------------------------------------------------------------------

`//The key001 is reachable for the robot now. `
<br/>
<br/>
`<(*,Self,key001) --> reachable>. :|:`
<br/>
<br/>
`11`
<br/>
<br/>
`//If the pick key001, the robot will hold key001. `
<br/>
<br/>
`<(^pick,key001) =/> <(*,Self,key001) --> hold>>. :|: `
<br/>
<br/>
`20`
<br/>
<br/>
`//If the key001 is reachable for the robot and the robot picks the key001, the robot may hold hey001.`
<br/>
<br/>
`//outputMustContain('<(&/,<(*,Self,key001) --> reachable>,+11,(^pick,key001)) =/> <(*,Self,key001) --> hold>>. :!11: %1.00;0.45%')`

---------------------------------------------------------------------------------------------

`//If the key001 is reachable for the robot and the robot picks the key001, the robot will hold hey001. `
<br/>
<br/>
`<(&/,<(*,Self,key001) --> reachable>,(^pick,key001)) =/> <(*,Self,key001) --> hold>>.`
<br/>
<br/>
`//Now the key001 is reachable. `
<br/>
<br/>
`<(*,Self,key001) --> reachable>. :|:  `
<br/>
<br/>
`1`
<br/>
<br/>
`//If the robot pick key001, it will hold key001.`
<br/>
<br/>
`//outputMustContain('<(^pick,key001) =/> <(*,Self,key001) --> hold>>. :!0: %1.00;0.81%')`

---------------------------------------------------------------------------------------------

`//If pick the key001 ,the robot will hold the key001. `
<br/>
<br/>
`<(^pick,key001) =/> <(*,Self,key001) --> hold>>. :|: %1.00;0.81% `
<br/>
<br/>
`//The goal is to hold key001.`
<br/>
<br/>
`<(*,Self,key001) --> hold>! `
<br/>
<br/>
`10`
<br/>
<br/>
`//The goal maybe to pick key001.`
<br/>
<br/>
`//outputMustContain('(^pick,key001)! %1.00;0.40%')`

---------------------------------------------------------------------------------------------

`//The robot picks key001. `
<br/>
<br/>
`(^pick,key001). :|:`
<br/>
<br/>
`//If pick the key001 ,the robot will hold the key001. `
<br/>
<br/>
`<(^pick,key001) =/> <(*,Self,key001) --> hold>>. :|: %1.00;0.81%`
<br/>
<br/>
`8`
<br/>
<br/>
`//The robot will hold the key001. `
<br/>
<br/>
`//outputMustContain('<(*,Self,key001) --> hold>. :!5: %1.00;0.73%')`

---------------------------------------------------------------------------------------------

`//The robot is holding key001. `
<br/>
<br/>
`<(*,Self,key001) --> hold>. :|: %1.00;0.73%`
<br/>
<br/>
`6`
<br/>
<br/>
`//The robot is holding key001`
<br/>
<br/>
`<(*,Self,key001) --> hold>. :|: %1.00;0.90%`
<br/>
<br/>
`10`
<br/>
<br/>
`//The robot is holding key001`
<br/>
<br/>
`//outputMustContain('<(*,Self,key001) --> hold>. :!6: %1.00;0.92%')`

---------------------------------------------------------------------------------------------

`//'a' is a type of 'A'`
<br/>
<br/>
`<a --> A>. :|:`
<br/>
<br/>
`10`
<br/>
<br/>
`//The robot picks key001`
<br/>
<br/>
`(^pick,{SELF},key001). :|: %1.00;0.90% `
<br/>
<br/>
`11`
<br/>
<br/>
`//The robot holds key001`
<br/>
<br/>
`<(*,Self,key001) --> hold>. :|: `
<br/>
<br/>
`16`
<br/>
<br/>
`//If 'a' is a type of 'A', and the robot pick key001, the robot may hold key001. `
<br/>
<br/>
`//outputMustContain('<(&/,<a --> A>,+10,(^pick,{SELF},key001),+11) =/> <(*,Self,key001) --> hold>>. :!21: %1.00;0.42%')`
<br/>
<br/>
`//adjusted +3 to +4 ^`

---------------------------------------------------------------------------------------------

`//If the robot pick key001, it will hold key001.`
<br/>
<br/>
`<(^pick,key001) =/> <(*,Self,key001) --> hold>>. :|: %1.00;0.81%`
<br/>
<br/>
`1`
<br/>
<br/>
`//If the robot pick key001, it may hold key001.`
<br/>
<br/>
`<(^pick,key001) =/> <(*,Self,key001) --> hold>>. :|: %1.00;0.45%`
<br/>
<br/>
`10`
<br/>
<br/>
`//If the robot pick key001, it will hold key001.`
<br/>
<br/>
`//outputMustContain('<(^pick,key001) =/> <(*,Self,key001) --> hold>>. :!1: %1.00;0.84%')`

---------------------------------------------------------------------------------------------

`//The key001 is reachable`
<br/>
<br/>
`<(*,Self,key001) --> reachable>. :|: `
<br/>
<br/>
`11`
<br/>
<br/>
`//If pick key001, the robot will hold key001.`
<br/>
<br/>
`<(^pick,key001) =/> <(*,Self,key001) --> hold>>. :|: %1.00;0.84%`
<br/>
<br/>
`17`
<br/>
<br/>
`//If key001 is reachable and the robot pick key001, it may hold key001.`
<br/>
<br/>
`//outputMustContain('<(&/,<(*,Self,key001) --> reachable>,+11,(^pick,key001)) =/> <(*,Self,key001) --> hold>>. :!11: %1.00;0.43%')`

---------------------------------------------------------------------------------------------

`//If key001 is reachable and the robot pick key001, it will hold key001.`
<br/>
<br/>
`<(&/,<(*,Self,key001) --> reachable>,(^pick,key001)) =/> <(*,Self,key001) --> hold>>. %1.00;0.90% `
<br/>
<br/>
`1`
<br/>
<br/>
`//If key001 is reachable and the robot pick key001, it may hold key001.`
<br/>
<br/>
`<(&/,<(*,Self,key001) --> reachable>,(^pick,key001)) =/> <(*,Self,key001) --> hold>>. %1.00;0.43% `
<br/>
<br/>
`1`
<br/>
<br/>
`//If key001 is reachable and the robot pick key001, it will hold key001.`
<br/>
<br/>
`//outputMustContain('<(&/,<(*,Self,key001) --> reachable>,(^pick,key001)) =/> <(*,Self,key001) --> hold>>. %1.00;0.91%')`

---------------------------------------------------------------------------------------------

`// Add operator`
<br/>
<br/>
`(^add,{SELF},2,3,?1)!`
<br/>
<br/>
`//outputMustContain('(^add,{SELF},2,3,5). :!0: %1.00;0.90%')`

---------------------------------------------------------------------------------------------

`// Count operator`
<br/>
<br/>
`(^count,{SELF},{a,b,c,d},?1)!`
<br/>
<br/>
`//outputMustContain('(^count,{SELF},{a,b,c,d},4). :!0: %1.00;0.90%')`

---------------------------------------------------------------------------------------------

`// Reflect operator`
<br/>
<br/>
`(^reflect,{SELF},<cat --> animal>,?1)!`
<br/>
<br/>
`10`
<br/>
<br/>
`//outputMustContain('(^reflect,{SELF},<cat --> animal>,<(*,cat,animal) --> inheritance>). :!0: %1.00;0.90%')`

---------------------------------------------------------------------------------------------

