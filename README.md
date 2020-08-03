# translator-from-Cyrillic-to-Latin-Fsharp
Translator from Cyrillic to Latin F#
Транслитер на F#

open System
let tes = "Иванов Иван"
let uppercase (tes : string) = tes.ToUpper()
let tes1 = tes |> uppercase
let ret = new System.Text.StringBuilder()
let rus = [|"А"; "Б"; "В"; "Г"; "Д"; "Е"; "Ё"; "Ж"; "З"; "И"; "Й"; "К"; "Л"; "М"; "Н"; "О"; "П"; "Р"; "С"; "Т"; "У"; "Ф"; "Х"; "Ц"; "Ч"; "Ш"; "Щ"; "Ъ"; "Ы"; "Ь"; "Э"; "Ю"; "Я"; " "|]
let eng = [|"a"; "b"; "v"; "g"; "d"; "e"; "e"; "j"; "z"; "i"; "y"; "k"; "l"; "m"; "n"; "o"; "p"; "r"; "s"; "t"; "u"; "f"; "h"; "c"; "ch"; "h"; "sh"; "9"; "y"; "6"; "e"; "yu"; "ya"; "."|]

let function1() = for j = 0 to tes1.Length-1 do
 for i = 0 to rus.Length-1 do
   let test1 = tes1.Substring(j, 1).Contains rus.[i]
   if test1 = true then ret.Append(eng.[i])|>ignore 
function1()
let result = ret.ToString()
printfn "%s" result
