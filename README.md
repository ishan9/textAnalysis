# textAnalysis
small demo app in perl

POST Request

POST Request consist of text which needs to be analysed.
The Api generates and returns a unique message id 
curl -H "Content-Type: application/json" -X POST -d '{"text":"wonderful beautiful awesome day"}' http://35.163.153.163/cgi-bin/textAnalysis/textanalyser

GET request

GET request to see the analysis of a particular text. message id is passed as query parameter 
The Api returns word frequency, vowel frequency, message sentiment, etc
curl -i -H "Accept: application/json" -H "Content-Type: application/json" http://35.163.153.163/cgi-bin/textAnalysis/textanalyser?id=112

Example response

curl -H "Content-Type: application/json" -X POST -d '{"text":"wonderful beautiful awesome day"}' http://35.163.153.163/cgi-bin/textAnalysis/textanalyser 
% Total % Received % Xferd Average Speed Time Time Time Current Dload Upload Total Spent Left Speed 100 62 0 20 100 42 10 22 0:00:01 0:00:01 --:--:-- 22 
{ "id" : "112" } 


curl -i -H "Accept: application/json" -H "Content-Type: application/json" http://35.163.153.163/cgi-bin/textAnalysis/textanalyser?id=112 
% Total % Received % Xferd Average Speed Time Time Time Current Dload Upload Total Spent Left Speed 100 446 0 446 0 0 571 0 --:--:-- --:--:-- --:--:-- 571HTTP/1.1 200 OK 
Date: Sun, 13 Aug 2017 23:00:45 GMT Server: Apache/2.2.32 (Amazon) Connection: close Transfer-Encoding: chunked Content-Type: text/plain; charset=UTF-8 { "word_freq" : { "wonderful" : 1, "day" : 1, "beautiful" : 1, "awesome" : 1 }, "status" : "completed", "sentiment" : "positive", "start_time" : "Sun Aug 13 22:59:16 2017", "vowel_freq" : { "e" : 4, "u" : 3, "a" : 3, "o" : 2, "i" : 1 }, "end_time" : "Sun Aug 13 22:59:17 2017", "text" : "wonderful beautiful awesome day", "id" : "112", "task_completed" : 4 }
