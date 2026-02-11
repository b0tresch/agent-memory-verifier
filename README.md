# Agent Memory Registry - Proof Verifier

Web UI for verifying Merkle proofs from the Agent Memory Registry hackathon project.

## What it does

- Verifies that a memory file was included in a specific checkpoint
- Computes file hash and validates Merkle proof
- Provides visual feedback on verification status
- Educational demo for hackathon judges

## Live Demo

🔗 **View Online:** https://htmlpreview.github.io/?https://github.com/b0tresch/agent-memory-verifier/blob/master/index.html

*(GitHub Pages pending manual enablement)*

## Usage

### Local Testing

```bash
cd ~/workspace/projects/hackathon-verifier
python3 -m http.server 8080
```

Then visit: http://localhost:8080

### Deployment Options

1. **GitHub Pages** (free, easy)
   ```bash
   git init
   git add .
   git commit -m "Add verification UI"
   gh repo create agent-memory-verifier --public --source=. --push
   # Enable GitHub Pages in repo settings
   ```

2. **Vercel** (free, fast)
   ```bash
   npm i -g vercel
   vercel --prod
   ```

3. **Netlify Drop** (free, instant)
   - Just drag the folder to https://app.netlify.com/drop

## Example Proof

Use data from actual checkpoint (2026-02-11 06:17 UTC):

**Merkle Root:**
```
0x1f7469f4017dcd8b40399fae44c79388e3dbe2a865d9ccaa97e7df63bcd239b0
```

**Transaction:**
```
0xe28be61a6287e168d6d4cb7108fb01ed9e6827ce0db5fb3f40b2e16a567861db
```

**Block:** 12053042

## How the Merkle Proof Works

1. Hash the file content: `SHA256(file_content)`
2. Combine with sibling hashes from proof (sorted order)
3. Hash pairs recursively until root is computed
4. Compare computed root with on-chain root

## Tech Stack

- Pure HTML/CSS/JS (no build step needed)
- ethers.js for cryptographic operations
- Responsive design (mobile-friendly)

## Next Steps

- [ ] Add example data for demo
- [ ] Deploy to public URL
- [ ] Add link to hackathon submission
- [ ] Include blockchain explorer link
- [ ] Add "View on Monad Explorer" button
