## API Report File for "@backstage/catalog-client"

> Do not edit this file. It is a report generated by [API Extractor](https://api-extractor.com/).

```ts
import { CompoundEntityRef } from '@backstage/catalog-model';
import { Entity } from '@backstage/catalog-model';

// @public
export type AddLocationRequest = {
  type?: string;
  target: string;
  dryRun?: boolean;
  presence?: 'optional' | 'required';
};

// @public
export type AddLocationResponse = {
  location: Location_2;
  entities: Entity[];
  exists?: boolean;
};

// @public
export const CATALOG_FILTER_EXISTS: unique symbol;

// @public
export interface CatalogApi {
  addLocation(
    location: AddLocationRequest,
    options?: CatalogRequestOptions,
  ): Promise<AddLocationResponse>;
  getEntities(
    request?: GetEntitiesRequest,
    options?: CatalogRequestOptions,
  ): Promise<GetEntitiesResponse>;
  getEntityAncestors(
    request: GetEntityAncestorsRequest,
    options?: CatalogRequestOptions,
  ): Promise<GetEntityAncestorsResponse>;
  // @deprecated
  getEntityByName(
    name: CompoundEntityRef,
    options?: CatalogRequestOptions,
  ): Promise<Entity | undefined>;
  getEntityByRef(
    entityRef: string | CompoundEntityRef,
    options?: CatalogRequestOptions,
  ): Promise<Entity | undefined>;
  getEntityFacets(
    request: GetEntityFacetsRequest,
    options?: CatalogRequestOptions,
  ): Promise<GetEntityFacetsResponse>;
  getLocationById(
    id: string,
    options?: CatalogRequestOptions,
  ): Promise<Location_2 | undefined>;
  getLocationByRef(
    locationRef: string,
    options?: CatalogRequestOptions,
  ): Promise<Location_2 | undefined>;
  refreshEntity(
    entityRef: string,
    options?: CatalogRequestOptions,
  ): Promise<void>;
  removeEntityByUid(
    uid: string,
    options?: CatalogRequestOptions,
  ): Promise<void>;
  removeLocationById(
    id: string,
    options?: CatalogRequestOptions,
  ): Promise<void>;
}

// @public
export class CatalogClient implements CatalogApi {
  constructor(options: {
    discoveryApi: {
      getBaseUrl(pluginId: string): Promise<string>;
    };
    fetchApi?: {
      fetch: typeof fetch;
    };
  });
  addLocation(
    { type, target, dryRun, presence }: AddLocationRequest,
    options?: CatalogRequestOptions,
  ): Promise<AddLocationResponse>;
  getEntities(
    request?: GetEntitiesRequest,
    options?: CatalogRequestOptions,
  ): Promise<GetEntitiesResponse>;
  getEntityAncestors(
    request: GetEntityAncestorsRequest,
    options?: CatalogRequestOptions,
  ): Promise<GetEntityAncestorsResponse>;
  getEntityByName(
    compoundName: CompoundEntityRef,
    options?: CatalogRequestOptions,
  ): Promise<Entity | undefined>;
  getEntityByRef(
    entityRef: string | CompoundEntityRef,
    options?: CatalogRequestOptions,
  ): Promise<Entity | undefined>;
  getEntityFacets(
    request: GetEntityFacetsRequest,
    options?: CatalogRequestOptions,
  ): Promise<GetEntityFacetsResponse>;
  getLocationById(
    id: string,
    options?: CatalogRequestOptions,
  ): Promise<Location_2 | undefined>;
  getLocationByRef(
    locationRef: string,
    options?: CatalogRequestOptions,
  ): Promise<Location_2 | undefined>;
  refreshEntity(
    entityRef: string,
    options?: CatalogRequestOptions,
  ): Promise<void>;
  removeEntityByUid(
    uid: string,
    options?: CatalogRequestOptions,
  ): Promise<void>;
  removeLocationById(
    id: string,
    options?: CatalogRequestOptions,
  ): Promise<void>;
}

// @public
export interface CatalogRequestOptions {
  // (undocumented)
  token?: string;
}

// @public
export const ENTITY_STATUS_CATALOG_PROCESSING_TYPE =
  'backstage.io/catalog-processing';

// @public
export interface GetEntitiesRequest {
  after?: string;
  fields?: string[] | undefined;
  filter?:
    | Record<string, string | symbol | (string | symbol)[]>[]
    | Record<string, string | symbol | (string | symbol)[]>
    | undefined;
  limit?: number;
  offset?: number;
}

// @public
export interface GetEntitiesResponse {
  // (undocumented)
  items: Entity[];
}

// @public
export interface GetEntityAncestorsRequest {
  // (undocumented)
  entityRef: string;
}

// @public
export interface GetEntityAncestorsResponse {
  // (undocumented)
  items: Array<{
    entity: Entity;
    parentEntityRefs: string[];
  }>;
  // (undocumented)
  rootEntityRef: string;
}

// @public
export interface GetEntityFacetsRequest {
  facets: string[];
  filter?:
    | Record<string, string | symbol | (string | symbol)[]>[]
    | Record<string, string | symbol | (string | symbol)[]>
    | undefined;
}

// @public
export interface GetEntityFacetsResponse {
  facets: Record<
    string,
    Array<{
      value: string;
      count: number;
    }>
  >;
}

// @public
type Location_2 = {
  id: string;
  type: string;
  target: string;
  presence?: 'optional' | 'required';
};
export { Location_2 as Location };
```
