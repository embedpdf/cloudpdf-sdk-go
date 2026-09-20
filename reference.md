# Reference
## Deployment
<details><summary><code>client.Deployment.LicenseStatus() -> *cloudpdf.DeploymentLicenseStatusResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
client.Deployment.LicenseStatus(
    context.TODO(),
)
```
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Doc
<details><summary><code>client.Doc.Head(DocID) -> *cloudpdf.DocHead200Response</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &cloudpdf.HeadDocRequest{
    DocID: "docId",
}
client.Doc.Head(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**docID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**documentPassword:** `*string` — Base64-encoded password for an encrypted document. Valid only with the API token (403 anywhere else). An encrypted document answers 422 DocPasswordRequired when the header is absent. Viewer doc JWTs use the SDK password-session flow instead.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Doc.Download(DocID, LayerName) -> string</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &cloudpdf.DownloadDocRequest{
    DocID: "docId",
    LayerName: "layerName",
}
client.Doc.Download(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**docID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**layerName:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**documentPassword:** `*string` — Base64-encoded password for an encrypted document. Valid only with the API token (403 anywhere else). An encrypted document answers 422 DocPasswordRequired when the header is absent. Viewer doc JWTs use the SDK password-session flow instead.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Doc.Manifest(DocID, LayerName) -> *cloudpdf.DocManifest200Response</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &cloudpdf.ManifestDocRequest{
    DocID: "docId",
    LayerName: "layerName",
}
client.Doc.Manifest(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**docID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**layerName:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**documentPassword:** `*string` — Base64-encoded password for an encrypted document. Valid only with the API token (403 anywhere else). An encrypted document answers 422 DocPasswordRequired when the header is absent. Viewer doc JWTs use the SDK password-session flow instead.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Doc.Render(DocID, LayerName, Pon) -> string</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Render parameters (viewport, format) pass as flat dotted query keys, e.g. `?viewport.kind=width&viewport.width=800`; the full grammar is documented with the viewer.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &cloudpdf.RenderDocRequest{
    DocID: "docId",
    LayerName: "layerName",
    Pon: 1,
}
client.Doc.Render(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**docID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**layerName:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**pon:** `int` 
    
</dd>
</dl>

<dl>
<dd>

**documentPassword:** `*string` — Base64-encoded password for an encrypted document. Valid only with the API token (403 anywhere else). An encrypted document answers 422 DocPasswordRequired when the header is absent. Viewer doc JWTs use the SDK password-session flow instead.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Doc.Text(DocID, LayerName, Pon) -> *cloudpdf.DocText200Response</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &cloudpdf.TextDocRequest{
    DocID: "docId",
    LayerName: "layerName",
    Pon: 1,
}
client.Doc.Text(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**docID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**layerName:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**pon:** `int` 
    
</dd>
</dl>

<dl>
<dd>

**documentPassword:** `*string` — Base64-encoded password for an encrypted document. Valid only with the API token (403 anywhere else). An encrypted document answers 422 DocPasswordRequired when the header is absent. Viewer doc JWTs use the SDK password-session flow instead.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Shares
<details><summary><code>client.Shares.Exchange(request) -> *cloudpdf.SharesExchange200Response</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Unauthenticated, but requires a browser Origin header, checked against the grant allowlist. Unknown, revoked, and disabled tokens are indistinguishable (404). Passphrase-protected grants return 422 SharePasswordRequired until `password` is supplied. Mounted only when the deployment can sign (HS256 mode).
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &cloudpdf.SharesExchangeRequest{
    ShareToken: "shareToken",
}
client.Shares.Exchange(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**shareToken:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**password:** `*string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Shares.List(TenantID) -> *cloudpdf.SharesList200Response</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &cloudpdf.ListSharesRequest{
    TenantID: "tenantId",
}
client.Shares.List(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**tenantID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**limit:** `*int` 
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**docID:** `*string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Shares.Create(TenantID, request) -> *cloudpdf.SharesCreate200Response</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

The returned share id IS the public share token. Mounted only when the deployment can sign (HS256 mode) — exchange mints session JWTs, so grants exist only where minting does.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &cloudpdf.SharesCreateRequest{
    TenantID: "tenantId",
    DocID: "docId",
    Scope: []string{
        "scope",
    },
}
client.Shares.Create(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**tenantID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**docID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**layerName:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**scope:** `[]string` 
    
</dd>
</dl>

<dl>
<dd>

**origins:** `[]string` 
    
</dd>
</dl>

<dl>
<dd>

**password:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**sessionTTLSeconds:** `*int` 
    
</dd>
</dl>

<dl>
<dd>

**expiresAt:** `*int` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Shares.Get(TenantID, ShareID) -> *cloudpdf.SharesGet200Response</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &cloudpdf.GetSharesRequest{
    TenantID: "tenantId",
    ShareID: "shareId",
}
client.Shares.Get(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**tenantID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**shareID:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Shares.Delete(TenantID, ShareID) -> error</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &cloudpdf.DeleteSharesRequest{
    TenantID: "tenantId",
    ShareID: "shareId",
}
client.Shares.Delete(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**tenantID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**shareID:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Shares.Update(TenantID, ShareID, request) -> *cloudpdf.SharesUpdate200Response</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &cloudpdf.SharesUpdateRequest{
    TenantID: "tenantId",
    ShareID: "shareId",
}
client.Shares.Update(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**tenantID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**shareID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**scope:** `[]string` 
    
</dd>
</dl>

<dl>
<dd>

**origins:** `[]string` 
    
</dd>
</dl>

<dl>
<dd>

**password:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**sessionTTLSeconds:** `*int` 
    
</dd>
</dl>

<dl>
<dd>

**disabled:** `*bool` 
    
</dd>
</dl>

<dl>
<dd>

**expiresAt:** `*int` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Tenants
<details><summary><code>client.Tenants.List() -> *cloudpdf.TenantsList200Response</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &cloudpdf.ListTenantsRequest{}
client.Tenants.List(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**limit:** `*int` 
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Tenants.Create(request) -> *cloudpdf.TenantsCreate200Response</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &cloudpdf.TenantsCreateRequest{
    ID: "id",
}
client.Tenants.Create(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**name:** `*string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Tenants.Get(TenantID) -> *cloudpdf.TenantsGet200Response</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &cloudpdf.GetTenantsRequest{
    TenantID: "tenantId",
}
client.Tenants.Get(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**tenantID:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Tenants.Delete(TenantID) -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Destroys the tenant and everything in its namespace — documents, layers, stored bytes, audit history. Irreversible.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &cloudpdf.DeleteTenantsRequest{
    TenantID: "tenantId",
}
client.Tenants.Delete(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**tenantID:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Tenants.Resume(TenantID) -> error</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &cloudpdf.ResumeTenantsRequest{
    TenantID: "tenantId",
}
client.Tenants.Resume(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**tenantID:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Tenants.Suspend(TenantID, request) -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Instantly reversible with resume. The API token is exempt, so a suspended tenant can still be inspected, exported, resumed, or deleted.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &cloudpdf.TenantsSuspendRequest{
    TenantID: "tenantId",
}
client.Tenants.Suspend(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**tenantID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**reason:** `*string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Tenants.Usage(TenantID) -> *cloudpdf.TenantsUsage200Response</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Facts only — no limits or billing state. Views count share exchanges plus authorized /v1/access grants, deduplicated across the two.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &cloudpdf.UsageTenantsRequest{
    TenantID: "tenantId",
}
client.Tenants.Usage(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**tenantID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**period:** `*string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Documents
<details><summary><code>client.Documents.List(TenantID) -> *cloudpdf.DocumentsList200Response</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &cloudpdf.ListDocumentsRequest{
    TenantID: "tenantId",
}
client.Documents.List(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**tenantID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**limit:** `*int` 
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**state:** `*cloudpdf.ListDocumentsRequestState` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Documents.Get(TenantID, ID) -> *cloudpdf.DocumentsGet200Response</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &cloudpdf.GetDocumentsRequest{
    TenantID: "tenantId",
    ID: "id",
}
client.Documents.Get(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**tenantID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Documents.Delete(TenantID, ID) -> error</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &cloudpdf.DeleteDocumentsRequest{
    TenantID: "tenantId",
    ID: "id",
}
client.Documents.Delete(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**tenantID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Documents.Commit(TenantID, ID, request) -> *cloudpdf.DocumentsCommit200Response</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &cloudpdf.DocumentsCommitRequest{
    TenantID: "tenantId",
    ID: "id",
    Sha256: "sha256",
}
client.Documents.Commit(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**tenantID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**sha256:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Documents.Download(TenantID, ID) -> string</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &cloudpdf.DownloadDocumentsRequest{
    TenantID: "tenantId",
    ID: "id",
}
client.Documents.Download(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**tenantID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Documents.Thumbnail(TenantID, ID) -> string</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &cloudpdf.ThumbnailDocumentsRequest{
    TenantID: "tenantId",
    ID: "id",
}
client.Documents.Thumbnail(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**tenantID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Documents.UploadProxy(TenantID, ID, request) -> *cloudpdf.DocumentsUploadProxy200Response</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

This bounded origin-mediated fallback must only be used after documents.init returns upload.kind=proxy. Auto mode prefers a presigned object-store PUT whenever available.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &cloudpdf.UploadProxyDocumentsRequest{
    TenantID: "tenantId",
    ID: "id",
    File: strings.NewReader(
        "",
    ),
}
client.Documents.UploadProxy(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**tenantID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Documents.ImportFrom(TenantID, request) -> *cloudpdf.DocumentsImportFrom200Response</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Default mode is synchronous and bounded: the response returns only after the transfer verified and committed (or failed). mode=async (connection sources only) answers 202 immediately and an in-process worker performs the transfer with leased, fenced retries; poll the document until ready/failed. The deployment import policy gates scheme, network range, and size; sources must declare a length. CloudPDF copies and owns the bytes — the source is never referenced in place. A 502 marks a retryable upstream failure: retry with the same idempotencyKey to resume the same document. URL sources are capabilities and never echoed back. Connection sources name operator-registered storage (bucket/prefix scope, allowed credential classes, and tenant bindings are deployment configuration); `revision` is provider-interpreted (S3 VersionId, GCS generation, Azure version id).
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &cloudpdf.DocumentsImportFromRequest{
    TenantID: "tenantId",
    Source: &cloudpdf.DocumentsImportFromRequestSource{
        URL: &cloudpdf.DocumentsImportFromRequestSourceURL{
            URL: "url",
        },
    },
}
client.Documents.ImportFrom(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**tenantID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**source:** `*cloudpdf.DocumentsImportFromRequestSource` — Where CloudPDF pulls the bytes from. The two shapes differ in WHO supplies the authority to read, not in which storage vendor holds the file.
    
</dd>
</dl>

<dl>
<dd>

**expected:** `*cloudpdf.DocumentsImportFromRequestExpected` — Integrity pins, enforced when present. When absent, the server-observed values become authoritative.
    
</dd>
</dl>

<dl>
<dd>

**metadata:** `map[string]any` 
    
</dd>
</dl>

<dl>
<dd>

**idempotencyKey:** `*string` — Retrying with the same key resumes the same document rather than importing a second copy — including after a 502.
    
</dd>
</dl>

<dl>
<dd>

**dedupMode:** `*cloudpdf.DocumentsImportFromRequestDedupMode` — always-create (default) creates a new document every time. reuse-existing returns a document that already holds the same content instead of storing it twice.
    
</dd>
</dl>

<dl>
<dd>

**docID:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**mode:** `*cloudpdf.DocumentsImportFromRequestMode` — sync (default) holds the response open for the whole transfer. async answers 202 with the document pending and transfers in the background; it requires a connection source, and filesystem connections additionally require expected.sha256.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Documents.Init(TenantID, request) -> *cloudpdf.DocumentsInit200Response</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &cloudpdf.DocumentsInitRequest{
    TenantID: "tenantId",
    ContentLength: 1.1,
    ContentSha256: "contentSha256",
}
client.Documents.Init(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**tenantID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**contentLength:** `float64` 
    
</dd>
</dl>

<dl>
<dd>

**contentSha256:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**metadata:** `map[string]any` 
    
</dd>
</dl>

<dl>
<dd>

**idempotencyKey:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**dedupMode:** `*cloudpdf.DocumentsInitRequestDedupMode` — always-create (default) creates a new document every time. reuse-existing returns a document that already holds the same content instead of storing it twice.
    
</dd>
</dl>

<dl>
<dd>

**docID:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**uploadTTLSec:** `*float64` 
    
</dd>
</dl>

<dl>
<dd>

**uploadPreference:** `*cloudpdf.DocumentsInitRequestUploadPreference` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Tokens
<details><summary><code>client.Tokens.Issue(TenantID, request) -> *cloudpdf.TokensIssue200Response</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

kind "tenant" requires the API token — authority mints only downward. Mounted only when the deployment can sign (HS256 mode); asymmetric deployments mint with their own private key.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &cloudpdf.IssueTokensRequest{
    TenantID: "tenantId",
    Body: &cloudpdf.TokensIssueRequest{
        Doc: &cloudpdf.TokensIssueRequestDoc{
            Sub: "sub",
            DocID: "docId",
            Scope: []string{
                "scope",
            },
            ExpiresIn: 1,
        },
    },
}
client.Tokens.Issue(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**tenantID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**request:** `*cloudpdf.TokensIssueRequest` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Tokens.Revoke(TenantID, Jti, request) -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Mounted only when the deployment enables token revocation.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &cloudpdf.TokensRevokeRequest{
    TenantID: "tenantId",
    Jti: "jti",
}
client.Tokens.Revoke(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**tenantID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**jti:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**reason:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**expiresAtSeconds:** `*int` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Doc Annotations
<details><summary><code>client.Doc.Annotations.ListAll(DocID, LayerName) -> *cloudpdf.DocAnnotationsListAll200Response</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns one entry per page plus the audit-log cursor for reconciling subsequent document events. Page order is unspecified; join by `pageState.pageObjectNumber` when display order matters.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &doc.ListAllAnnotationsRequest{
    DocID: "docId",
    LayerName: "layerName",
}
client.Doc.Annotations.ListAll(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**docID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**layerName:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**documentPassword:** `*string` — Base64-encoded password for an encrypted document. Valid only with the API token (403 anywhere else). An encrypted document answers 422 DocPasswordRequired when the header is absent. Viewer doc JWTs use the SDK password-session flow instead.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Doc.Annotations.List(DocID, LayerName, Pon) -> *cloudpdf.DocAnnotationsList200Response</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &doc.ListAnnotationsRequest{
    DocID: "docId",
    LayerName: "layerName",
    Pon: 1,
}
client.Doc.Annotations.List(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**docID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**layerName:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**pon:** `int` 
    
</dd>
</dl>

<dl>
<dd>

**documentPassword:** `*string` — Base64-encoded password for an encrypted document. Valid only with the API token (403 anywhere else). An encrypted document answers 422 DocPasswordRequired when the header is absent. Viewer doc JWTs use the SDK password-session flow instead.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Doc.Annotations.Create(DocID, LayerName, Pon, request) -> *cloudpdf.DocAnnotationsCreate200Response</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Doc JWTs may instead carry collab scopes (annotations:create:self, …) that refine per-annotation authorship rules; the API token is exempt from both.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &doc.CreateAnnotationsRequest{
    DocID: "docId",
    LayerName: "layerName",
    Pon: 1,
    Body: map[string]any{
        "key": "value",
    },
}
client.Doc.Annotations.Create(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**docID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**layerName:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**pon:** `int` 
    
</dd>
</dl>

<dl>
<dd>

**documentPassword:** `*string` — Base64-encoded password for an encrypted document. Valid only with the API token (403 anywhere else). An encrypted document answers 422 DocPasswordRequired when the header is absent. Viewer doc JWTs use the SDK password-session flow instead.
    
</dd>
</dl>

<dl>
<dd>

**request:** `cloudpdf.DocAnnotationsCreateRequest` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Doc.Annotations.Delete(DocID, LayerName, Pon, AnnotKey) -> *cloudpdf.DocAnnotationsDelete200Response</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &doc.DeleteAnnotationsRequest{
    DocID: "docId",
    LayerName: "layerName",
    Pon: 1,
    AnnotKey: "annotKey",
}
client.Doc.Annotations.Delete(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**docID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**layerName:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**pon:** `int` 
    
</dd>
</dl>

<dl>
<dd>

**annotKey:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**documentPassword:** `*string` — Base64-encoded password for an encrypted document. Valid only with the API token (403 anywhere else). An encrypted document answers 422 DocPasswordRequired when the header is absent. Viewer doc JWTs use the SDK password-session flow instead.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Doc.Annotations.Update(DocID, LayerName, Pon, AnnotKey, request) -> *cloudpdf.DocAnnotationsUpdate200Response</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &doc.UpdateAnnotationsRequest{
    DocID: "docId",
    LayerName: "layerName",
    Pon: 1,
    AnnotKey: "annotKey",
    Body: map[string]any{
        "key": "value",
    },
}
client.Doc.Annotations.Update(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**docID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**layerName:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**pon:** `int` 
    
</dd>
</dl>

<dl>
<dd>

**annotKey:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**documentPassword:** `*string` — Base64-encoded password for an encrypted document. Valid only with the API token (403 anywhere else). An encrypted document answers 422 DocPasswordRequired when the header is absent. Viewer doc JWTs use the SDK password-session flow instead.
    
</dd>
</dl>

<dl>
<dd>

**request:** `cloudpdf.DocAnnotationsUpdateRequest` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Doc.Annotations.ExportAppearance(DocID, LayerName, Pon, request) -> string</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &doc.ExportAppearanceAnnotationsRequest{
    DocID: "docId",
    LayerName: "layerName",
    Pon: 1,
    Body: map[string]any{
        "string": map[string]any{
            "key": "value",
        },
    },
}
client.Doc.Annotations.ExportAppearance(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**docID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**layerName:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**pon:** `int` 
    
</dd>
</dl>

<dl>
<dd>

**documentPassword:** `*string` — Base64-encoded password for an encrypted document. Valid only with the API token (403 anywhere else). An encrypted document answers 422 DocPasswordRequired when the header is absent. Viewer doc JWTs use the SDK password-session flow instead.
    
</dd>
</dl>

<dl>
<dd>

**request:** `cloudpdf.DocAnnotationsExportAppearanceRequest` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Doc.Annotations.Flatten(DocID, LayerName, Pon, request) -> *cloudpdf.DocAnnotationsFlatten200Response</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &doc.FlattenAnnotationsRequest{
    DocID: "docId",
    LayerName: "layerName",
    Pon: 1,
    Body: map[string]any{
        "key": "value",
    },
}
client.Doc.Annotations.Flatten(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**docID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**layerName:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**pon:** `int` 
    
</dd>
</dl>

<dl>
<dd>

**documentPassword:** `*string` — Base64-encoded password for an encrypted document. Valid only with the API token (403 anywhere else). An encrypted document answers 422 DocPasswordRequired when the header is absent. Viewer doc JWTs use the SDK password-session flow instead.
    
</dd>
</dl>

<dl>
<dd>

**request:** `cloudpdf.DocAnnotationsFlattenRequest` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Doc Forms
<details><summary><code>client.Doc.Forms.Get(DocID, LayerName) -> *cloudpdf.DocFormsGet200Response</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &doc.GetFormsRequest{
    DocID: "docId",
    LayerName: "layerName",
}
client.Doc.Forms.Get(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**docID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**layerName:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**documentPassword:** `*string` — Base64-encoded password for an encrypted document. Valid only with the API token (403 anywhere else). An encrypted document answers 422 DocPasswordRequired when the header is absent. Viewer doc JWTs use the SDK password-session flow instead.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Doc.Forms.ExportData(DocID, LayerName) -> string</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &doc.ExportDataFormsRequest{
    DocID: "docId",
    LayerName: "layerName",
}
client.Doc.Forms.ExportData(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**docID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**layerName:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**format:** `*doc.ExportDataFormsRequestFormat` 
    
</dd>
</dl>

<dl>
<dd>

**documentPassword:** `*string` — Base64-encoded password for an encrypted document. Valid only with the API token (403 anywhere else). An encrypted document answers 422 DocPasswordRequired when the header is absent. Viewer doc JWTs use the SDK password-session flow instead.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Doc.Forms.ImportData(DocID, LayerName, request) -> *cloudpdf.DocFormsImportData200Response</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &doc.ImportDataFormsRequest{
    DocID: "docId",
    LayerName: "layerName",
    Body: map[string]any{
        "key": "value",
    },
}
client.Doc.Forms.ImportData(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**docID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**layerName:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**documentPassword:** `*string` — Base64-encoded password for an encrypted document. Valid only with the API token (403 anywhere else). An encrypted document answers 422 DocPasswordRequired when the header is absent. Viewer doc JWTs use the SDK password-session flow instead.
    
</dd>
</dl>

<dl>
<dd>

**request:** `cloudpdf.DocFormsImportDataRequest` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Doc.Forms.Reset(DocID, LayerName, FieldKey) -> *cloudpdf.DocFormsReset200Response</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &doc.ResetFormsRequest{
    DocID: "docId",
    LayerName: "layerName",
    FieldKey: "fieldKey",
}
client.Doc.Forms.Reset(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**docID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**layerName:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**fieldKey:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**documentPassword:** `*string` — Base64-encoded password for an encrypted document. Valid only with the API token (403 anywhere else). An encrypted document answers 422 DocPasswordRequired when the header is absent. Viewer doc JWTs use the SDK password-session flow instead.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Doc.Forms.SetValue(DocID, LayerName, FieldKey, request) -> *cloudpdf.DocFormsSetValue200Response</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &doc.SetValueFormsRequest{
    DocID: "docId",
    LayerName: "layerName",
    FieldKey: "fieldKey",
    Body: map[string]any{
        "key": "value",
    },
}
client.Doc.Forms.SetValue(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**docID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**layerName:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**fieldKey:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**documentPassword:** `*string` — Base64-encoded password for an encrypted document. Valid only with the API token (403 anywhere else). An encrypted document answers 422 DocPasswordRequired when the header is absent. Viewer doc JWTs use the SDK password-session flow instead.
    
</dd>
</dl>

<dl>
<dd>

**request:** `cloudpdf.DocFormsSetValueRequest` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Doc Metadata
<details><summary><code>client.Doc.Metadata.Get(DocID, LayerName) -> *cloudpdf.DocMetadataGet200Response</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &doc.GetMetadataRequest{
    DocID: "docId",
    LayerName: "layerName",
}
client.Doc.Metadata.Get(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**docID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**layerName:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**documentPassword:** `*string` — Base64-encoded password for an encrypted document. Valid only with the API token (403 anywhere else). An encrypted document answers 422 DocPasswordRequired when the header is absent. Viewer doc JWTs use the SDK password-session flow instead.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Doc Pages
<details><summary><code>client.Doc.Pages.SetScale(DocID, LayerName, Pon, request) -> *cloudpdf.DocPagesSetScale200Response</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &doc.DocPagesSetScaleRequest{
    DocID: "docId",
    LayerName: "layerName",
    Pon: 1,
}
client.Doc.Pages.SetScale(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**docID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**layerName:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**pon:** `int` 
    
</dd>
</dl>

<dl>
<dd>

**documentPassword:** `*string` — Base64-encoded password for an encrypted document. Valid only with the API token (403 anywhere else). An encrypted document answers 422 DocPasswordRequired when the header is absent. Viewer doc JWTs use the SDK password-session flow instead.
    
</dd>
</dl>

<dl>
<dd>

**measure:** `*doc.DocPagesSetScaleRequestMeasure` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Doc.Pages.Viewports(DocID, LayerName, Pon) -> cloudpdf.DocPagesViewports200Response</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &doc.ViewportsPagesRequest{
    DocID: "docId",
    LayerName: "layerName",
    Pon: 1,
}
client.Doc.Pages.Viewports(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**docID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**layerName:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**pon:** `int` 
    
</dd>
</dl>

<dl>
<dd>

**documentPassword:** `*string` — Base64-encoded password for an encrypted document. Valid only with the API token (403 anywhere else). An encrypted document answers 422 DocPasswordRequired when the header is absent. Viewer doc JWTs use the SDK password-session flow instead.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Doc.Pages.Delete(DocID, LayerName, request) -> *cloudpdf.DocPagesDelete200Response</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &doc.DeletePagesRequest{
    DocID: "docId",
    LayerName: "layerName",
    Body: map[string]any{
        "key": "value",
    },
}
client.Doc.Pages.Delete(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**docID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**layerName:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**documentPassword:** `*string` — Base64-encoded password for an encrypted document. Valid only with the API token (403 anywhere else). An encrypted document answers 422 DocPasswordRequired when the header is absent. Viewer doc JWTs use the SDK password-session flow instead.
    
</dd>
</dl>

<dl>
<dd>

**request:** `cloudpdf.DocPagesDeleteRequest` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Doc.Pages.Extract(DocID, LayerName, request) -> string</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

A read, not a mutation: the source document is untouched and no event is published. Body is `{"pageObjectNumbers": number[]}`; the response body is the new PDF.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &doc.ExtractPagesRequest{
    DocID: "docId",
    LayerName: "layerName",
    Body: map[string]any{
        "string": map[string]any{
            "key": "value",
        },
    },
}
client.Doc.Pages.Extract(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**docID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**layerName:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**documentPassword:** `*string` — Base64-encoded password for an encrypted document. Valid only with the API token (403 anywhere else). An encrypted document answers 422 DocPasswordRequired when the header is absent. Viewer doc JWTs use the SDK password-session flow instead.
    
</dd>
</dl>

<dl>
<dd>

**request:** `cloudpdf.DocPagesExtractRequest` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Doc.Pages.Flatten(DocID, LayerName, request) -> *cloudpdf.DocPagesFlatten200Response</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &doc.FlattenPagesRequest{
    DocID: "docId",
    LayerName: "layerName",
    Body: map[string]any{
        "key": "value",
    },
}
client.Doc.Pages.Flatten(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**docID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**layerName:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**documentPassword:** `*string` — Base64-encoded password for an encrypted document. Valid only with the API token (403 anywhere else). An encrypted document answers 422 DocPasswordRequired when the header is absent. Viewer doc JWTs use the SDK password-session flow instead.
    
</dd>
</dl>

<dl>
<dd>

**request:** `cloudpdf.DocPagesFlattenRequest` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Doc.Pages.Insert(DocID, LayerName, request) -> *cloudpdf.DocPagesInsert200Response</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Multipart mutation envelope: a `body` field holding `{"destIndex"?: number}` (omitted → append) plus a `resource:source` file part carrying the standalone PDF whose pages are copied in. The inserted copies get fresh page object numbers, returned in insertion order.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &doc.InsertPagesRequest{
    DocID: "docId",
    LayerName: "layerName",
    File: strings.NewReader(
        "",
    ),
}
client.Doc.Pages.Insert(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**docID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**layerName:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**documentPassword:** `*string` — Base64-encoded password for an encrypted document. Valid only with the API token (403 anywhere else). An encrypted document answers 422 DocPasswordRequired when the header is absent. Viewer doc JWTs use the SDK password-session flow instead.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Doc.Pages.InsertBlank(DocID, LayerName, request) -> *cloudpdf.DocPagesInsertBlank200Response</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Body is `{"size": {"width", "height"}, "count"?, "destIndex"?}` — size in PDF points, count in [1, 100], destIndex omitted → append.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &doc.InsertBlankPagesRequest{
    DocID: "docId",
    LayerName: "layerName",
    Body: map[string]any{
        "key": "value",
    },
}
client.Doc.Pages.InsertBlank(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**docID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**layerName:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**documentPassword:** `*string` — Base64-encoded password for an encrypted document. Valid only with the API token (403 anywhere else). An encrypted document answers 422 DocPasswordRequired when the header is absent. Viewer doc JWTs use the SDK password-session flow instead.
    
</dd>
</dl>

<dl>
<dd>

**request:** `cloudpdf.DocPagesInsertBlankRequest` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Doc.Pages.Move(DocID, LayerName, request) -> *cloudpdf.DocPagesMove200Response</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &doc.MovePagesRequest{
    DocID: "docId",
    LayerName: "layerName",
    Body: map[string]any{
        "key": "value",
    },
}
client.Doc.Pages.Move(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**docID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**layerName:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**documentPassword:** `*string` — Base64-encoded password for an encrypted document. Valid only with the API token (403 anywhere else). An encrypted document answers 422 DocPasswordRequired when the header is absent. Viewer doc JWTs use the SDK password-session flow instead.
    
</dd>
</dl>

<dl>
<dd>

**request:** `cloudpdf.DocPagesMoveRequest` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Doc.Pages.SetName(DocID, LayerName, request) -> *cloudpdf.DocPagesSetName200Response</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &doc.SetNamePagesRequest{
    DocID: "docId",
    LayerName: "layerName",
    Body: map[string]any{
        "key": "value",
    },
}
client.Doc.Pages.SetName(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**docID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**layerName:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**documentPassword:** `*string` — Base64-encoded password for an encrypted document. Valid only with the API token (403 anywhere else). An encrypted document answers 422 DocPasswordRequired when the header is absent. Viewer doc JWTs use the SDK password-session flow instead.
    
</dd>
</dl>

<dl>
<dd>

**request:** `cloudpdf.DocPagesSetNameRequest` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Doc.Pages.RemoveName(DocID, LayerName, request) -> *cloudpdf.DocPagesRemoveName200Response</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &doc.RemoveNamePagesRequest{
    DocID: "docId",
    LayerName: "layerName",
    Body: map[string]any{
        "key": "value",
    },
}
client.Doc.Pages.RemoveName(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**docID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**layerName:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**documentPassword:** `*string` — Base64-encoded password for an encrypted document. Valid only with the API token (403 anywhere else). An encrypted document answers 422 DocPasswordRequired when the header is absent. Viewer doc JWTs use the SDK password-session flow instead.
    
</dd>
</dl>

<dl>
<dd>

**request:** `cloudpdf.DocPagesRemoveNameRequest` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Doc.Pages.Rotate(DocID, LayerName, request) -> *cloudpdf.DocPagesRotate200Response</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &doc.RotatePagesRequest{
    DocID: "docId",
    LayerName: "layerName",
    Body: map[string]any{
        "key": "value",
    },
}
client.Doc.Pages.Rotate(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**docID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**layerName:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**documentPassword:** `*string` — Base64-encoded password for an encrypted document. Valid only with the API token (403 anywhere else). An encrypted document answers 422 DocPasswordRequired when the header is absent. Viewer doc JWTs use the SDK password-session flow instead.
    
</dd>
</dl>

<dl>
<dd>

**request:** `cloudpdf.DocPagesRotateRequest` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Doc Redactions
<details><summary><code>client.Doc.Redactions.Apply(DocID, LayerName, request) -> *cloudpdf.DocRedactionsApply200Response</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &doc.ApplyRedactionsRequest{
    DocID: "docId",
    LayerName: "layerName",
    Body: map[string]any{
        "key": "value",
    },
}
client.Doc.Redactions.Apply(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**docID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**layerName:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**documentPassword:** `*string` — Base64-encoded password for an encrypted document. Valid only with the API token (403 anywhere else). An encrypted document answers 422 DocPasswordRequired when the header is absent. Viewer doc JWTs use the SDK password-session flow instead.
    
</dd>
</dl>

<dl>
<dd>

**request:** `cloudpdf.DocRedactionsApplyRequest` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Doc Signatures
<details><summary><code>client.Doc.Signatures.List(DocID, LayerName) -> *cloudpdf.DocSignaturesList200Response</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Describes the bytes the layer is over: the base version's signatures plus the layer's own edits as the last revision. Signed bytes (contents, digests, revision prefixes) are served per base version under /versions.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &doc.ListSignaturesRequest{
    DocID: "docId",
    LayerName: "layerName",
}
client.Doc.Signatures.List(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**docID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**layerName:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**documentPassword:** `*string` — Base64-encoded password for an encrypted document. Valid only with the API token (403 anywhere else). An encrypted document answers 422 DocPasswordRequired when the header is absent. Viewer doc JWTs use the SDK password-session flow instead.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Doc.Signatures.Abort(DocID, LayerName, SigningID) -> *cloudpdf.DocSignaturesAbort200Response</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &doc.AbortSignaturesRequest{
    DocID: "docId",
    LayerName: "layerName",
    SigningID: "signingId",
}
client.Doc.Signatures.Abort(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**docID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**layerName:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**signingID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**documentPassword:** `*string` — Base64-encoded password for an encrypted document. Valid only with the API token (403 anywhere else). An encrypted document answers 422 DocPasswordRequired when the header is absent. Viewer doc JWTs use the SDK password-session flow instead.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Doc.Signatures.Complete(DocID, LayerName, SigningID, request) -> *cloudpdf.DocSignaturesComplete200Response</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

`cms` is the detached CMS over the prepared digest, base64. `expectedVersion` must be what prepare returned. Idempotent by signing id: the same CMS again answers `already-completed`. Every layer of the document then sits over the new version; refetch the manifest after a completion.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &doc.DocSignaturesCompleteRequest{
    DocID: "docId",
    LayerName: "layerName",
    SigningID: "signingId",
    Cms: "cms",
    ExpectedVersion: &doc.DocSignaturesCompleteRequestExpectedVersion{
        BaseSha256: "baseSha256",
        EditsVersion: 1,
    },
}
client.Doc.Signatures.Complete(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**docID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**layerName:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**signingID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**documentPassword:** `*string` — Base64-encoded password for an encrypted document. Valid only with the API token (403 anywhere else). An encrypted document answers 422 DocPasswordRequired when the header is absent. Viewer doc JWTs use the SDK password-session flow instead.
    
</dd>
</dl>

<dl>
<dd>

**cms:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**expectedVersion:** `*doc.DocSignaturesCompleteRequestExpectedVersion` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Doc.Signatures.Analysis(DocID, LayerName) -> *cloudpdf.DocSignaturesAnalysis200Response</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Exactly one of `since.signature=<index>` or `since.revision=<index>`; the layer's pending edits are the end. `level=fill|annotate|lta|none` evaluates exploratorily and never becomes a verdict. For history between two base revisions use the version analysis.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &doc.AnalysisSignaturesRequest{
    DocID: "docId",
    LayerName: "layerName",
}
client.Doc.Signatures.Analysis(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**docID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**layerName:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**sinceSignature:** `*int` 
    
</dd>
</dl>

<dl>
<dd>

**sinceRevision:** `*int` 
    
</dd>
</dl>

<dl>
<dd>

**level:** `*doc.AnalysisSignaturesRequestLevel` 
    
</dd>
</dl>

<dl>
<dd>

**documentPassword:** `*string` — Base64-encoded password for an encrypted document. Valid only with the API token (403 anywhere else). An encrypted document answers 422 DocPasswordRequired when the header is absent. Viewer doc JWTs use the SDK password-session flow instead.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Doc.Signatures.Prepare(DocID, LayerName, request) -> *cloudpdf.DocSignaturesPrepare200Response</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

The multipart envelope: a JSON `body` part (field, subFilter, digest, contentsSize, signer, certify, lock, appearance) and an optional `resource:<key>` PDF part the body's `appearance.resource` names. A certification (`certify.permission`) additionally requires `doc.sign.certify`. The layer is read-only until the signing completes, is aborted, or expires (15 minutes). A layer behind the document head cannot sign (StaleBase).
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &doc.PrepareSignaturesRequest{
    DocID: "docId",
    LayerName: "layerName",
    File: strings.NewReader(
        "",
    ),
}
client.Doc.Signatures.Prepare(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**docID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**layerName:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**documentPassword:** `*string` — Base64-encoded password for an encrypted document. Valid only with the API token (403 anywhere else). An encrypted document answers 422 DocPasswordRequired when the header is absent. Viewer doc JWTs use the SDK password-session flow instead.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Doc Versions
<details><summary><code>client.Doc.Versions.List(DocID) -> *cloudpdf.DocVersionsList200Response</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Every completed signature publishes a new version. Never cached: the list grows.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &doc.ListVersionsRequest{
    DocID: "docId",
}
client.Doc.Versions.List(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**docID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**documentPassword:** `*string` — Base64-encoded password for an encrypted document. Valid only with the API token (403 anywhere else). An encrypted document answers 422 DocPasswordRequired when the header is absent. Viewer doc JWTs use the SDK password-session flow instead.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Doc.Versions.Analysis(DocID, Sha) -> *cloudpdf.DocVersionsAnalysis200Response</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Exactly one of `since.signature` / `since.revision`; `until=<revision>` defaults to the last. The same answer for every layer and every caller.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &doc.AnalysisVersionsRequest{
    DocID: "docId",
    Sha: "sha",
}
client.Doc.Versions.Analysis(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**docID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**sha:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**sinceSignature:** `*int` 
    
</dd>
</dl>

<dl>
<dd>

**sinceRevision:** `*int` 
    
</dd>
</dl>

<dl>
<dd>

**level:** `*doc.AnalysisVersionsRequestLevel` 
    
</dd>
</dl>

<dl>
<dd>

**until:** `*int` 
    
</dd>
</dl>

<dl>
<dd>

**policy:** `*int` 
    
</dd>
</dl>

<dl>
<dd>

**documentPassword:** `*string` — Base64-encoded password for an encrypted document. Valid only with the API token (403 anywhere else). An encrypted document answers 422 DocPasswordRequired when the header is absent. Viewer doc JWTs use the SDK password-session flow instead.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Doc.Versions.Download(DocID, Sha) -> string</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &doc.DownloadVersionsRequest{
    DocID: "docId",
    Sha: "sha",
}
client.Doc.Versions.Download(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**docID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**sha:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**documentPassword:** `*string` — Base64-encoded password for an encrypted document. Valid only with the API token (403 anywhere else). An encrypted document answers 422 DocPasswordRequired when the header is absent. Viewer doc JWTs use the SDK password-session flow instead.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Doc.Versions.Revision(DocID, Sha, Index) -> string</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &doc.RevisionVersionsRequest{
    DocID: "docId",
    Sha: "sha",
    Index: 1,
}
client.Doc.Versions.Revision(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**docID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**sha:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**index:** `int` 
    
</dd>
</dl>

<dl>
<dd>

**documentPassword:** `*string` — Base64-encoded password for an encrypted document. Valid only with the API token (403 anywhere else). An encrypted document answers 422 DocPasswordRequired when the header is absent. Viewer doc JWTs use the SDK password-session flow instead.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Doc.Versions.Signatures(DocID, Sha) -> *cloudpdf.DocVersionsSignatures200Response</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &doc.SignaturesVersionsRequest{
    DocID: "docId",
    Sha: "sha",
}
client.Doc.Versions.Signatures(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**docID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**sha:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**documentPassword:** `*string` — Base64-encoded password for an encrypted document. Valid only with the API token (403 anywhere else). An encrypted document answers 422 DocPasswordRequired when the header is absent. Viewer doc JWTs use the SDK password-session flow instead.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Doc.Versions.SignatureContents(DocID, Sha, FieldKey) -> string</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

`fieldKey` is the field's fully qualified name, token-text encoded (the same encoding attachment keys use).
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &doc.SignatureContentsVersionsRequest{
    DocID: "docId",
    Sha: "sha",
    FieldKey: "fieldKey",
}
client.Doc.Versions.SignatureContents(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**docID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**sha:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**fieldKey:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**documentPassword:** `*string` — Base64-encoded password for an encrypted document. Valid only with the API token (403 anywhere else). An encrypted document answers 422 DocPasswordRequired when the header is absent. Viewer doc JWTs use the SDK password-session flow instead.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Doc.Versions.SignatureDigest(DocID, Sha, FieldKey, Algorithm) -> string</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

What a CMS verifier compares its message digest to.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &doc.SignatureDigestVersionsRequest{
    DocID: "docId",
    Sha: "sha",
    FieldKey: "fieldKey",
    Algorithm: doc.SignatureDigestVersionsRequestAlgorithmSha1,
}
client.Doc.Versions.SignatureDigest(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**docID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**sha:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**fieldKey:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**algorithm:** `*doc.SignatureDigestVersionsRequestAlgorithm` 
    
</dd>
</dl>

<dl>
<dd>

**documentPassword:** `*string` — Base64-encoded password for an encrypted document. Valid only with the API token (403 anywhere else). An encrypted document answers 422 DocPasswordRequired when the header is absent. Viewer doc JWTs use the SDK password-session flow instead.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

