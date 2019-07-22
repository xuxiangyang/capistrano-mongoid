require "bundler/gem_tasks"
task :default => :spec

namespace :db do
  namespace :mongoid do
    desc "create shard for Mongo"
    task shard: :environment do
      ::Mongoid.models.each do |model|
        next unless !model.embedded? || model.cyclic?
        next if model.shard_key_fields.blank?

        admin_db = model.collection.client.list_mongo_databases(name: :admin).first
        admin_db.command(enableSharding: model.collection.database.name)
        admin_db.command(shardCollection: model.collection.namespace, key: Hash[model.shard_key_fields.map { |field| [field, 1] }])
        Mongoid.logger.info("MONGOID shard for #{model.collection.namespace}")
      end
    end
  end
end
