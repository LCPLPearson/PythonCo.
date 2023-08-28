PAD1: active directory\
PAD2: objects\
PAD3: schema\
PAD4: LDAP\
PAD5: Admin\
PAD6: disable\
PAD7: get-aduser\
PAD8: DS\
-----
WADB8: 21-1004336348-1177238915-682003330\
WADB1: get-adgroup\
WADB2: get-aduser -filter 'name -like "*"'
WADB5: Search-ADAccount\
-----
WASA: command:Get-ADUser -Filter "AccountExpirationDate -le '$(Get-Date)'" -Properties AccountExpirationDate, answer: Krause,Page\
-----
