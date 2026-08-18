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

**dedupMode:** `*cloudpdf.DocumentsInitRequestDedupMode` 
    
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

