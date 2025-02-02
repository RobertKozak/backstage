## API Report File for "@backstage/plugin-search-backend-module-elasticsearch"

> Do not edit this file. It is a report generated by [API Extractor](https://api-extractor.com/).

```ts
/// <reference types="node" />

import { BatchSearchEngineIndexer } from '@backstage/plugin-search-backend-node';
import { Client } from '@elastic/elasticsearch';
import { Config } from '@backstage/config';
import type { ConnectionOptions } from 'tls';
import { IndexableDocument } from '@backstage/plugin-search-common';
import { Logger as Logger_2 } from 'winston';
import { SearchEngine } from '@backstage/plugin-search-common';
import { SearchQuery } from '@backstage/plugin-search-common';
import { SearchResultSet } from '@backstage/plugin-search-common';

// Warning: (ae-missing-release-tag) "ElasticSearchClientOptions" is exported by the package, but it is missing a release tag (@alpha, @beta, @public, or @internal)
// Warning: (ae-unresolved-link) The @link reference could not be resolved: The package "@backstage/plugin-search-backend-module-elasticsearch" does not have an export "ElasticSearchEngine"
//
// @public
export interface ElasticSearchClientOptions {
  // Warning: (ae-forgotten-export) The symbol "ElasticSearchAgentOptions" needs to be exported by the entry point index.d.ts
  //
  // (undocumented)
  agent?: ElasticSearchAgentOptions | ((opts?: any) => unknown) | false;
  // Warning: (ae-forgotten-export) The symbol "ElasticSearchAuth" needs to be exported by the entry point index.d.ts
  //
  // (undocumented)
  auth?: ElasticSearchAuth;
  // (undocumented)
  cloud?: {
    id: string;
    username?: string;
    password?: string;
  };
  // (undocumented)
  compression?: 'gzip';
  // Warning: (ae-forgotten-export) The symbol "ElasticSearchConnectionConstructor" needs to be exported by the entry point index.d.ts
  //
  // (undocumented)
  Connection?: ElasticSearchConnectionConstructor;
  // (undocumented)
  disablePrototypePoisoningProtection?: boolean | 'proto' | 'constructor';
  // (undocumented)
  enableMetaHeader?: boolean;
  // (undocumented)
  headers?: Record<string, any>;
  // (undocumented)
  maxRetries?: number;
  // (undocumented)
  name?: string | symbol;
  // Warning: (ae-forgotten-export) The symbol "ElasticSearchNodeOptions" needs to be exported by the entry point index.d.ts
  //
  // (undocumented)
  node?:
    | string
    | string[]
    | ElasticSearchNodeOptions
    | ElasticSearchNodeOptions[];
  // (undocumented)
  nodeFilter?: (connection: any) => boolean;
  // (undocumented)
  nodes?:
    | string
    | string[]
    | ElasticSearchNodeOptions
    | ElasticSearchNodeOptions[];
  // (undocumented)
  nodeSelector?: ((connections: any[]) => any) | string;
  // (undocumented)
  opaqueIdPrefix?: string;
  // (undocumented)
  pingTimeout?: number;
  // (undocumented)
  provider?: 'aws' | 'elastic';
  // (undocumented)
  proxy?: string | URL;
  // (undocumented)
  requestTimeout?: number;
  // (undocumented)
  resurrectStrategy?: 'ping' | 'optimistic' | 'none';
  // (undocumented)
  sniffEndpoint?: string;
  // (undocumented)
  sniffInterval?: number | boolean;
  // (undocumented)
  sniffOnConnectionFault?: boolean;
  // (undocumented)
  sniffOnStart?: boolean;
  // (undocumented)
  ssl?: ConnectionOptions;
  // (undocumented)
  suggestCompression?: boolean;
  // Warning: (ae-forgotten-export) The symbol "ElasticSearchTransportConstructor" needs to be exported by the entry point index.d.ts
  //
  // (undocumented)
  Transport?: ElasticSearchTransportConstructor;
}

// @public (undocumented)
export class ElasticSearchSearchEngine implements SearchEngine {
  constructor(
    elasticSearchClientOptions: ElasticSearchClientOptions,
    aliasPostfix: string,
    indexPrefix: string,
    logger: Logger_2,
  );
  // Warning: (ae-forgotten-export) The symbol "ElasticSearchOptions" needs to be exported by the entry point index.d.ts
  //
  // (undocumented)
  static fromConfig({
    logger,
    config,
    aliasPostfix,
    indexPrefix,
  }: ElasticSearchOptions): Promise<ElasticSearchSearchEngine>;
  // (undocumented)
  getIndexer(type: string): Promise<ElasticSearchSearchEngineIndexer>;
  newClient<T>(create: (options: ElasticSearchClientOptions) => T): T;
  // (undocumented)
  query(query: SearchQuery): Promise<SearchResultSet>;
  // Warning: (ae-forgotten-export) The symbol "ElasticSearchQueryTranslator" needs to be exported by the entry point index.d.ts
  //
  // (undocumented)
  setTranslator(translator: ElasticSearchQueryTranslator): void;
  // Warning: (ae-forgotten-export) The symbol "ConcreteElasticSearchQuery" needs to be exported by the entry point index.d.ts
  //
  // (undocumented)
  protected translator(query: SearchQuery): ConcreteElasticSearchQuery;
}

// Warning: (ae-missing-release-tag) "ElasticSearchSearchEngineIndexer" is exported by the package, but it is missing a release tag (@alpha, @beta, @public, or @internal)
//
// @public (undocumented)
export class ElasticSearchSearchEngineIndexer extends BatchSearchEngineIndexer {
  constructor(options: ElasticSearchSearchEngineIndexerOptions);
  // (undocumented)
  finalize(): Promise<void>;
  // (undocumented)
  index(documents: IndexableDocument[]): Promise<void>;
  // (undocumented)
  readonly indexName: string;
  // (undocumented)
  initialize(): Promise<void>;
}

// Warning: (ae-missing-release-tag) "ElasticSearchSearchEngineIndexerOptions" is exported by the package, but it is missing a release tag (@alpha, @beta, @public, or @internal)
//
// @public (undocumented)
export type ElasticSearchSearchEngineIndexerOptions = {
  type: string;
  indexPrefix: string;
  indexSeparator: string;
  alias: string;
  logger: Logger_2;
  elasticSearchClient: Client;
};
```
