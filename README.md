# mongo-db
> show dbs
admin   0.000GB
config  0.000GB
local   0.000GB
> use music
switched to db music
> db.createCollection("songdetails")
{ "ok" : 1 }
> show collection
uncaught exception: Error: don't know how to show [collection] :
shellHelper.show@src/mongo/shell/utils.js:1211:11
shellHelper@src/mongo/shell/utils.js:838:15
@(shellhelp2):1:1
> show collections
songdetails
> db.songdetails.insert([{"song name":"thaniye thananthaniye","film":"rhythm","music director":"a.r.rahman","singer":"shankar mahadevan"},{"song name":"evano oruvan","film":"alai payuthey","music director":"a.r.rahman","singer":"swarnalatha"},{"song name":"roja poonthottam","film":"kannukul nilavu","music director":"ilayaraaja","singer":["unni krishnan","anuradha sriram"]},{"song name":"vennilavae vennilavae vinnaithaandi","film":"minsara kanavu","music director":"a.r.rahman","singer":["hariharan","sadhana sargam"]},{"song name":"sollamal thottu chellum thendral","film":"dheena","music director":"yuvan shankar raja","singer":"hariharan"}])
BulkWriteResult({
	"writeErrors" : [ ],
	"writeConcernErrors" : [ ],
	"nInserted" : 5,
	"nUpserted" : 0,
	"nMatched" : 0,
	"nModified" : 0,
	"nRemoved" : 0,
	"upserted" : [ ]
})
> db.songdetails.find().pretty()
{
	"_id" : ObjectId("611631176b2e758295e7495e"),
	"song name" : "thaniye thananthaniye",
	"film" : "rhythm",
	"music director" : "a.r.rahman",
	"singer" : "shankar mahadevan"
}
{
	"_id" : ObjectId("611631176b2e758295e7495f"),
	"song name" : "evano oruvan",
	"film" : "alai payuthey",
	"music director" : "a.r.rahman",
	"singer" : "swarnalatha"
}
{
	"_id" : ObjectId("611631176b2e758295e74960"),
	"song name" : "roja poonthottam",
	"film" : "kannukul nilavu",
	"music director" : "ilayaraaja",
	"singer" : [
		"unni krishnan",
		"anuradha sriram"
	]
}
{
	"_id" : ObjectId("611631176b2e758295e74961"),
	"song name" : "vennilavae vennilavae vinnaithaandi",
	"film" : "minsara kanavu",
	"music director" : "a.r.rahman",
	"singer" : [
		"hariharan",
		"sadhana sargam"
	]
}
{
	"_id" : ObjectId("611631176b2e758295e74962"),
	"song name" : "sollamal thottu chellum thendral",
	"film" : "dheena",
	"music director" : "yuvan shankar raja",
	"singer" : "hariharan"
}
> db.songdetails.find({"music director":"a.r.rahman","singer":"unni krishnan"}).pretty()
> db.songdetails.find({"music director":"a.r.rahman","singer":"unni krishnan"}).pretty()
> db.songdetails.remove({"_id" : ObjectId("611631176b2e758295e7495e")})
WriteResult({ "nRemoved" : 1 })
> db,songdetails.insert({"song name":"en iniya thanimaiye","flim":"teddy","music director":santhosh narayanan"
uncaught exception: SyntaxError: missing } after property list :
@(shell):1:98
> db,songdetails.insert({"song name":"en iniya thanimaiye","flim":"teddy","music director":santhosh narayanan","singer":"a.r.rahman"})
uncaught exception: SyntaxError: missing } after property list :
@(shell):1:98
> db,songdetails.insert({"song name":"en iniya thanimaiye","flim":"teddy","music director":santhosh narayanan"db.songdetails,insert({"song name":"en iniya thanimaiye","flim":"teddy","music director":santhosh narayanan","singar":"santhosh narayanan"})
uncaught exception: SyntaxError: missing } after property list :
@(shell):1:98
>  db.songdetails.insert([{"song name":"en iniya thanimaiye","film":"teddy","music director":"a.r.rahman","singer":"santhosh narayanan"})
... 
... db,songdetails.insert({"song name":"en iniya thanimaiye","flim":"teddy","music director":santhosh narayanan"db.songdetails,insert({"song name":"en iniya thanimaiye","flim":"teddy","music director":santhosh narayanan","singar":"santhosh narayanan"})
... db.songdetails.insert([{"song name":"thaniye thananthaniye","film":"rhythm","music director":"a.r.rahman","singer":"shankar mahadevan"},{"song name":"evano oruvan","film":"alai payuthey","music director":"a.r.rahman","singer":"swarnalatha"},{"song name":"roja poonthottam","film":"kannukul nilavu","music director":"ilayaraaja","singer":["unni krishnan","anuradha sriram"]},{"song name":"vennilavae vennilavae vinnaithaandi","film":"minsara kanavu","music director":"a.r.rahman","singer":["hariharan","sadhana sargam"]},{"song name":"sollamal thottu chellum thendral","film":"dheena","music director":"yuvan shankar raja","singer":"hariharan"}])
... 
... 
> 
> 
> 
> 
> 
> 
> 
> 
> db.songdetails.insert([{"song name":"nathiye nathiye","film":"rhythm","music director":"a.r.rahman","singer":"santhosh narayanan"}
... 
... 
> 
> db,songdetails.insert({"song name":"en iniya thanimaiye","flim":"teddy","music director":santhosh narayanan"db.songdetails,insert({"song name":"en iniya thanimaiye","flim":"teddy","music director":santhosh narayanan","singar":"santhosh narayanan"})
uncaught exception: SyntaxError: missing } after property list :
@(shell):1:98
> db.songdetails.find({"flim":"minsara kanavu","singer":"hariharan"}).pretty()
> 
> db.songdetails.find({"flim":"Minsara kanavu","singer":"Hariharan"}).pretty()
> 
> show collections
songdetails
> db.songdetails.distinct("singer")
[
	"anuradha sriram",
	"hariharan",
	"sadhana sargam",
	"swarnalatha",
	"unni krishnan"
]

