Get-ChildItem -Path "C:\Program Files\Microsoft\Exchange Server\V15\FrontEnd\HttpProxy" -Recurse | Where-Object {$_.LastWriteTime -gt (Get-Date).AddDays(-30)}
