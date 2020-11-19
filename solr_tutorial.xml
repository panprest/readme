#menjalankan solr
solr start

atau

solr start -p <port>

#membuat core / collection
solr create -c <namacore>

atau

solr create -c <namacore> -d <namaconfigset>

configset ada di server/configset

#membuat configset schema.xml
copy configset
paste

isinya diganti

cari   <codecFactory class="solr.SchemaCodecFactory"/>
 paste ini dibawahnya <schemaFactory class="ClassicIndexSchemaFactory"/>
 jadi seperti ini
 
   <codecFactory class="solr.SchemaCodecFactory"/>
  <schemaFactory class="ClassicIndexSchemaFactory"/>
  
 jangan lupa hapus add-schema-fields dari add-unknown-fields-to-the-schema
 
dari ini 

 <updateRequestProcessorChain name="add-unknown-fields-to-the-schema" default="${update.autoCreateFields:true}"
           processor="uuid,remove-blank,field-name-mutating,parse-boolean,parse-long,parse-double,parse-date,add-schema-fields">
    <processor class="solr.LogUpdateProcessorFactory"/>
    <processor class="solr.DistributedUpdateProcessorFactory"/>
    <processor class="solr.RunUpdateProcessorFactory"/>
  </updateRequestProcessorChain>
  
  menjadi ini
  
   <updateRequestProcessorChain name="add-unknown-fields-to-the-schema" default="${update.autoCreateFields:true}"
           processor="uuid,remove-blank,field-name-mutating,parse-boolean,parse-long,parse-double,parse-date">
    <processor class="solr.LogUpdateProcessorFactory"/>
    <processor class="solr.DistributedUpdateProcessorFactory"/>
    <processor class="solr.RunUpdateProcessorFactory"/>
  </updateRequestProcessorChain>
  
  jangan lupa tuliskan field2 yang didaftarkan di schema.xml
