require 'rake'
require 'cql'

task :default => [:dbcreate]

task :dbcreate do
  keyspace_definition = File.open("cql/keyspace_definition.cql", "rb").read
  table_definition = File.open("cql/table_definition.cql", "rb").read
  
  client = Cql::Client.new.start!
  client.execute(keyspace_definition)
  client.use('oink')
  client.execute(table_definition)
end