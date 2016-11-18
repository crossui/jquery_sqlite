# jquery_sqlite
jquery sqlite v1.0.0

/*
 examples:

//获取db对象,连接数据库 test，分配5M大小
 var db = $.sqlite('testDB',null,1024*1024*5);

//创建表
 db.init('chat_ecord',[
     //{name:'id',type:'integer primary key autoincrement'},   //会自动生成唯一的ID字段
     {name:'name',type:'text'},
     {name:'link',type:'text'},
     {name:'cover',type:'text'},
     {name:'updatetime',type:'integer'},
     {name:'orders',type:'integer'}
 ]);

//判断表是否存在
 db.existsTable('chat_ecord',function(t){
     for(var i in t[0]){
         if(t[0][i]){
            console.info('yes');
         }
     }
 });

//插入表字段
 db.addFields([
     {name:'youname',type:'text'},
     {name:'cityid',type:'text'}
 ]);


//修改表名
 db.renameTable('chat_ecord','chat_demo');

//删除表
 db.switchTable('chat_text').dropTable();

//切换表 (操作表前要先切换,支持链式操作)
 db.switchTable('chat_text');

//插入数据
 db.switchTable('chat_text').insertData([
     {
         name:'a1111a',
         link:'s2222s',
         updatetime:new Date().getTime()
     },
     {
         name:'b33333b',
         link:'k44444k',
         updatetime:new Date().getTime()
     }
 ]);

//根据条件更新数据 (不存在则插入:第二个参数为true)
 db.switchTable('chat_demo').where({name:'ff'}).saveData({name:'ff'},true,function(result){
    //$('#bb').html(result[0]);
    console.log(result[0]);    //影响条数
 });

//删除数据 (不用条件,可以清空表里所有的数据)
 db.switchTable('chat_demo').where({name:'aa'}).deleteData(function(result){
    console.log(result[0]);     //删除条数
 });

//获取数据
 db.switchTable('chat_demo').where({name:'aa'}).getData(null,function(result){
    console.log(result);    //result为Array
 });

//


*/
