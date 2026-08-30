# The A²OK World Kindness Gazette

The monthly newspaper of the A²OK World civilization.
Live at **kindnessgazette.com**.

## How this repository is arranged

```
index.html            the current issue — this is what kindnessgazette.com serves
issues/v01n01/        a permanent copy of Volume 1, Number 1
netlify.toml          deploy settings
```

The root `index.html` is always the newest issue. Every issue also keeps a
permanent copy under `issues/` so that a link printed on paper, sent in an
email or cited by another publication still works years later.

## Publishing a new issue

1. Copy the current `index.html` into `issues/vXXnXX/index.html`
2. Replace the root `index.html` with the new issue
3. Commit and push

Netlify redeploys on push. No build step — the site is plain HTML.

## Where the photographs live

No images are stored in this repository. Every photograph is delivered from
Cloudinary and cropped by the URL itself:

```
https://res.cloudinary.com/aok-world/image/upload/w_760,h_460,c_fill,g_auto,f_auto,q_auto/gazette/v01n01/<name>
```

`g_auto` finds the subject of the photograph and crops around it, so one
uploaded image serves every size the paper needs without being cut by hand.

Photograph names follow the key in `AOK_Gazette_Photo_Naming_Key.md`, kept in
the project. The short version:

```
b3s1c1-pantry-furniture-showroom-ai
│  │ │  │                        └── origin: -ai synthetic, -pub publisher, -own ours
│  │ │  └── what it shows
│  │ └── cell of the contact sheet
│  └── which sheet
└── which batch
```

To change a photograph, upload a replacement to Cloudinary under the same
name. The page updates with no code change and no redeploy.

## Standing rules

- Every claim the Gazette makes in its own voice is confirmed against the
  original publisher before it runs.
- Every carried story links home to the paper that reported it.
- A photograph is never published without a rights basis recorded in Airtable.
