## Day 1
get-command ##lists all commands##
get-verb ##lists all verbs##
get-command -Verb get ##lists all commands with verb get##
get-command -Noun Process ##lists all command with noun process##
get-childitem -path C:\Users\student\Desktop ##Lists the directory##
get-help ##help file##
update-help
get-help Get-Printer -full

### Ahead Day1
$x = get-process
$a = "cat dog"
($x).GetType()
$a -is [array]
$x.count
$array1= -5..10
$array = @()
$array1[$array.length -1

$employee1 = @{First = "Mary"; Last = "Hopper"; ID = "001"; Job = "Software Developer"}
$employee2 = @{First = "John"; Last = "Willams"; ID = "002"; Job = "Web Developer"}
$employee1["username"] = "mhopper001"
$employee2["username"] = "jwilliams002"
$employee3 = @{First = "Alex"; Last = "Moran"; ID = "003"; Job = "Software Developer"}
$employee1.Job = "Software Lead"

$a = ((Get-Random -Minimum -10 -Maximum 0)..(Get-Random -Minimum 1 -Maximum 20))
[array]::Reverse($a)
echo $a


### Thursday Excercises
Function Get-OrdinalDate
$date=(get=date).dateyear
...?...

get-suarenum([Int])$num)
{$result = $num * $num
$result
}

Function Get-Product($val1,$val2,$val3) {
  return $val1 * $val2 * $val3
  }

Function Get-MissingSide($a,$b) {
  return [math]::sqrt

Function Get-AngleSum ($a, $b){
return 180 - ($a + $b)
}

Function Get-UserInfo {
  param [Paraneter(janfa

Function Get-LongestNmae {
  Begin { 
  #count = 0
  $states = @()
}
Process { while($count -lt 3) {
$res = Read-Host "Enter a U.S. State"
$count += 1
}
End {
$list = $states | sort _property Length - descending
foreach($state in $list) {
"$state': " + $state.length

function get-urlinfo {
get-content "HOME\Desktop\dns.txt" | ?{$_ -match 'www\..*\.{com\ord\net' } | %

}

