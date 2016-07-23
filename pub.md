##pub  发布数据   
<br>
<hr style=" height:12px;border:none;border-top:4px solid #A9A9A9;" />     
在 DataHub 网站发布数据主题（ repo ）后，可通过pub命令在客户端发布数据集（ item ）、发布数据包（ tag ）。
###1.1 发布item
在发布item时需要指定在哪个repo下发布item，item所在的datahubpool，以及datahubpool下的目录，item的接入属性 accesstype，item描述（ comment ），数据类型（ supplystyle）。若属性未指定，则默认为private；若描述未指定，则默认为空；数据类型为指定，则默认为批量类型。    
 
#####输入
	datahub pub $REPOSITORY/$DATAITEM $DATAPOOL://$LOCATION --accesstype=[ public、 private]  --comment=$comment   --supplystyle=[ flow、 api、batch]
#####输出  
    %msg       	
#####例子  
    bash-3.2#datahub pub datahubrepo1/datahubitem1 datahubdp1://decitem1 --comment="帮助文档样例item描述" --supplystyle=private --accesstype=batch
	DataHub : Successed in publishing.  


###1.2 发布tag
在发布tag时需要指定在哪个 repo/item 下发布 tag ，源文件名称，tag描述（  comment ）。描述若未指定，则默认为空。      

* tag 源文件必须位于 item 目录下。  
* 每个 item 下的 tag 必须为同一种类型，且必须为item发布时指定的 supplystyle ，可以为流式（ flow ）、 api 、批量（ batch ）中的一种。
 

#####输入
	datahub pub $REPOSITORY/$DATAITEM:$Tag $TAGDETAIL --comment=$comment
#####输出  
    %msg       	
#####例子  
    bash-3.2# datahub pub datahubrepo1/datahubitem1:datahubtag1 datahubtag --comment=帮助文档样例tag描述
	DataHub : Successed in publishing.  

