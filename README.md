# Shoebox 3D

Private receipt and invoice sorter for freelancers, with an interactive 3D view. It runs an open-weight AI model on your own laptop, so your receipts never leave your computer. No upload, no account, no per-receipt fee.

**Live demo:** https://YOUR-USERNAME.github.io/shoebox-local-receipts/shoebox3d.html

## What it does

1. Paste text from receipts, invoices or emails. Separate each one with a line of `---`.
2. A local open model reads each receipt and finds the vendor, date, total and currency.
3. Each receipt flies out of a 3D shoebox and lands on a tower for its category (Software, Travel, Meals, Equipment and more).
4. The towers grow with your spending. Hover a tower to see its total.
5. Fix any category, then download a CSV for your accountant.

## 3D controls

- **Drag** to rotate the scene.
- **Scroll or pinch** to zoom.
- **Hover** a tower to see its category total.
- **Reset view** brings the camera back.
- **Hide panels** gives a full-screen view of the towers.

## Three ways to run it

| Engine | Needs | Good for |
|---|---|---|
| Ollama on your computer | Ollama installed | Fastest and most accurate |
| In-browser model (WebLLM) | Chrome or Edge with WebGPU | Nothing to install |
| Quick rules only | Nothing | Instant demo, no AI |

### Setup for Ollama

```bash
ollama pull qwen2.5:3b
```

Start Ollama with `OLLAMA_ORIGINS=*` so the page is allowed to talk to it, then open `shoebox3d.html` and choose the Ollama engine.

### Quick try without any setup

1. Open `shoebox3d.html`.
2. Click **Load samples**.
3. Choose **Quick rules only**.
4. Click **Sort receipts** and watch the receipts fly into the towers.

## Why open models matter here

- **Privacy:** client invoices and amounts stay on your laptop.
- **Cost:** no API bill that grows with every receipt.
- **Offline:** works without internet after the first setup.
- **Control:** swap the model, change the categories, or fine-tune on your own books. Nobody can change the pricing on you.

## Project files

- `index.html` is the landing page.
- `shoebox3d.html` is the 3D app.
- `shoebox.html` is the simple 2D app.
- `shoebox-poster.svg` is the poster.

## Offline 3D

The 3D view loads three.js from a CDN. To use it fully offline, download `three.min.js` (r128) and place it next to `shoebox3d.html`. The app loads it automatically if the online copy fails.

## Notes

Small models can misread messy receipts, so always check the items marked "check this". Category suggestions are not tax advice.

Built with open-weight models (Qwen2.5), Ollama, WebLLM and three.js.

## License

MIT