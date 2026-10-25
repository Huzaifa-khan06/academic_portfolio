# Huzaifa Khan — Academic Portfolio (Final Editable Version)

This version preserves the existing website layout. Removed: bundled duplicate styles/scripts/data and both .bat launchers.

## Open website
Double-click `index.html` in Chrome or Edge. Internet is only needed for optional Google Fonts.

## Where to edit
- **data.js** — all public biography, projects, exhibitions, photographs, links, and achievements.
- **styles.css** — colors, cards, fonts and layout (leave it untouched to keep the existing UI).
- **app.js** — functionality, navigation and galleries (leave untouched unless adding features).
- **index.html** — HTML skeleton only. No need to edit for projects or photos.

IMPORTANT: Edit these files in THIS final folder. Do not edit an earlier single-file standalone HTML and expect `data.js` changes to appear.

## Add a profile picture
1. Copy your photo to `assets/images/profile/huzaifa.jpg`.
2. Open `data.js` and set `profileImage: 'assets/images/profile/huzaifa.jpg',`.

## Add a photo to an existing project
1. Copy `mediloop-cover.jpg` to `assets/images/projects/`.
2. Find `id:'smart-mediloop'` under `projects:[` in `data.js`.
3. Set `image:'assets/images/projects/mediloop-cover.jpg'`.
4. Replace `gallery:[]` with `gallery:[{src:'assets/images/projects/mediloop-demo.jpg',caption:'Demonstration of Smart Mediloop'}]`; make sure to copy the demo photo too.
5. Save and refresh your browser (Ctrl+R).

## Add a new project
Copy ONE existing project object inside `projects:[ ... ]` in `data.js` and paste it after the last item separated by a comma. Change every field, especially the UNIQUE `id` (lowercase letters and hyphens only). Keep the fields `id,title,category,label,year,summary,description,problem,approach,contribution,technologies,status,image,gallery,featured`. Choose category from an existing item so filters work, or create your own category. Set `featured:true` to highlight it on the homepage. Project detail navigation is created automatically.

Example new project (copy INSIDE `projects` array; ensure neighboring objects have commas):
```js
{
  id:'my-new-project', title:'My New Project', category:'Mobile & Software',
  label:'Academic project', year:'2026', summary:'Brief one-line summary.',
  description:'Longer description.', problem:'Problem solved.',
  approach:'How it works.', contribution:'My own role.',
  technologies:['Flutter','Firebase'], status:'Academic project',
  image:'assets/images/projects/my-new-cover.jpg',
  gallery:[{src:'assets/images/projects/my-new-demo.jpg',caption:'Project demonstration'}],
  featured:false
}
```

## Add an exhibition
Copy an existing record in the `exhibitions:[ ... ]` array in `data.js` and change its UNIQUE id, title, place, date, kicker, description and `related` (the `id` of a project, or empty string). Put exhibition pictures in `assets/images/exhibitions/` and set:
```js
images:[
  {src:'assets/images/exhibitions/event-01.jpg',caption:'Demonstrating my project'},
  {src:'assets/images/exhibitions/event-02.jpg',caption:'Exhibition presentation'}
]
```

## Helpful tips
- Paths are relative to the `index.html` folder. Use forward slashes `/` and match exact filenames.
- Keep photos as JPG or WebP (PNG is best for UI screenshots), ideally below ~500 KB for gallery photographs.
- Do not publicly upload home address, national ID, date of birth or sensitive work infrastructure details.
- If a page becomes blank after a change, undo the last edit in `data.js` (missing quotes or commas are common). Open Chrome F12 > Console to read the error.
- Back up the whole folder before large edits.

## Publish
Upload all files/folders together to a static host like GitHub Pages. `index.html` must be at the site's root. Hash-based links make routes compatible with static hosting.
