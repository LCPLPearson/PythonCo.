## Practice Test

<# 1 #>
function q1($var1,$var2,$var3,$var4) {
$total = ($var1 * $var2 * $var3 * $var4)
return $total
    <# Return the product of the arguments #>
}
function q2($arr,$rows,$cols,$key) {
foreach ($i in $arr) {
if($i[0] -eq $key) {
return $i[9]
    }
    }
    return -1
    <# Search the 2 dimensional array for the first occurance of key at column index 0
       and return the value at column index 9 of the same row.
       Return -1 if the key is not found.
    #>
}
function q3 {
$vals = @()
do {
    $val = Read-Host
    if($val -ne -1) {
    $vals += $val
    }
    } until ($val -eq -1)
    return $($vals | Measure-Object -Maximum).Maximum

    <# In a loop, prompt the user to enter positive integers one at time.
       Stop when the user enters a -1. Return the maximum positive
       value that was entered."
	#>
}
function q4($filename,$whichline) {
Get-Content $filename | Select-Object -Index $whichline
    <# Return the line of text from the file given by the `$filename
	   argument that corresponds to the line number given by `$whichline.
	   The first line in the file corresponds to line number 0."
	#>
}
function q5($path) {
Get-ChildItem -Path $path | Sort-Object Name
    <# Return the child items from the given path sorted
       ascending by their Name
	#>
}
function q6 {
$sum = 0
$input | foreach { $sum += $_ }
return $sum

    <# Return the sum of all elements provided on the pipeline
	#>
}
function q7 {
Get-Command -Noun Process
	<# Return only those commands whose noun is process #>
}
function q8($adjective) {
return "Powershell is $adjective"
    <# Return the string 'PowerShell is ' followed by the adjective given
	   by the `$adjective argument
	#>    
}
function q9($addr) {

if ($addr -match '((25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\.){3}(25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)') {

return $True

} 

return $False


	<# Return `$true when the given argument is a valid IPv4 address,
	   otherwise return `$false. For the purpose of this function, regard
	   addresses where all octets are in the range 0-255 inclusive to
	   be valid.
	#>
}
function q10 ($filepath,$lasthash) {
$newhash = Get-FileHash $filepath 
if ($newhash -match $lasthash){
return $false }
return $true
    <# Return `$true if the contents of the file given in the
       `$filepath argument have changed since `$lasthash was
       computed. `$lasthash is the previously computed SHA256
       hash (as a string) of the contents of the file. #>
}

## Test Review Notes

functionq $($file,$line) {
<# Return the lin eof text from the file give by the $file
argument that begins with the text specified by $line. 
If no line in the file begins with the '$line text, return #null.' #>

$content = get-content $gile
foreach ($i in $content {
  if ($i.startswith($line)){
  return i
  }
  return $null
  }

  function q($arr) {
  <# Combine the provided '$arr argument into a string separated by a '/' between each element and return this string #>}
  {
  return $arr -join('/')

  function q () {
  <#Return the processes sorted descending by their Proccess Name #> }
  {
  return Get-Process | Sort-Object -Property name -Descending

  function q($arr,$rows,$cols,$key {
  search the array for the first occurance of $key at column index 0 and return the value at column index 9 of the same row.
  Return -1 if the $key is not found.
  {
  foreach ($i in $arr) {
    if($i[0] -eq $key) {
    return $1[9]
    }
  }
return -1

<#Get todays date in year month number and day of the month in yyyymmdd format(Custom date w/ -Uformat)#>
{
$fmt = '%Y$m%d'
return Get-Date -Uformat $fmt
}

#Provided on the pipeline
$_
#or
$input

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

