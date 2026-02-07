for ($i=1; $i -le 50; $i++) {
$code = curl.exe -s -o $null -w "%{http_code}" `
  --location "http://localhost:8080/api/transaction/create" `
--header "Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJyb2xlIjoiVVNFUiIsInVzZXJJZCI6MSwic3ViIjoiYWthc2hAZ21haWwuY29tIiwiaWF0IjoxNzcwNDUyODY3LCJleHAiOjE3NzA1MzkyNjd9.YJYXbsJz7MTo40QxtqfQXOdvPiaJRktHVMQVRZCu9d4" `
  --header "Content-Type: application/json" `
--data "{ `"senderId`":3, `"receiverId`":2, `"amount`":5000.0 }"

Write-Host "Request $i -> $code"
}

use this is powershell to check if rate limiting is working fine or not.