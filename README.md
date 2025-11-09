# Multi-Platform Matrix Build Demo

This repository demonstrates a GitHub Actions workflow with matrix build strategy across multiple platforms and Node.js versions.

## Author
Email: 24f2002696@ds.study.iitm.ac.in

## Workflow Features

### Matrix Strategy
The workflow builds across:
- **Operating Systems**: Ubuntu, macOS, Windows
- **Node.js Versions**: 16, 18, 20
- **Total Combinations**: 9 parallel builds

### Build Artifacts
Each matrix job generates:
- `build-info.json` - Build metadata
- `output.txt` - Build summary
- `app.js` - Sample application

All artifacts are uploaded with the naming convention:
```
build-15f1563-{platform}-node{version}
```

### Workflow Structure
1. **matrix-build** job runs 9 parallel builds
2. Each build:
   - Sets up the specified Node.js version
   - Executes the `matrix-15f1563` step
   - Generates build artifacts
   - Uploads artifacts with unique names
3. **aggregate-results** job:
   - Downloads all artifacts
   - Creates a summary report
   - Uploads the summary as an additional artifact

## How to Use

1. The workflow triggers automatically on:
   - Push to main/master branch
   - Pull requests
   - Manual trigger (workflow_dispatch)

2. View results in the Actions tab
3. Download artifacts from completed workflow runs

## Workflow File Location
`.github/workflows/matrix-build.yml`

## Requirements Met
✅ Matrix build with 9 variants (3 OS × 3 Node versions)  
✅ Parallel execution across all matrix combinations  
✅ Unique artifacts with `build-15f1563-` prefix  
✅ Step identifier `matrix-15f1563` included  
✅ Non-empty artifacts with actual build content  
✅ README.md with email address

## Sample Artifacts
- `build-15f1563-linux-node16`
- `build-15f1563-linux-node18`
- `build-15f1563-linux-node20`
- `build-15f1563-macos-node16`
- `build-15f1563-macos-node18`
- `build-15f1563-macos-node20`
- `build-15f1563-windows-node16`
- `build-15f1563-windows-node18`
- `build-15f1563-windows-node20`
- `build-15f1563-summary`

Total: 10 artifacts per workflow run
```

4. Click **"Commit changes"**

### Step 3: Trigger the Workflow

1. Go to the **"Actions"** tab in your repository

2. You should see "Multi-Platform Matrix Build" workflow

3. Click on it, then click **"Run workflow"** button (top right)

4. Select branch "main" and click **"Run workflow"**

5. Wait for all 9 matrix jobs + 1 aggregate job to complete (takes 2-5 minutes)

### Step 4: Verify Artifacts

1. Once the workflow completes, click on the workflow run

2. Scroll down to see **10 artifacts** listed:
   - build-15f1563-linux-node16
   - build-15f1563-linux-node18
   - build-15f1563-linux-node20
   - build-15f1563-macos-node16
   - build-15f1563-macos-node18
   - build-15f1563-macos-node20
   - build-15f1563-windows-node16
   - build-15f1563-windows-node18
   - build-15f1563-windows-node20
   - build-15f1563-summary

### Step 5: Submit

Once all jobs are green ✅ and artifacts are uploaded, submit:
```
https://github.com/24f2002696/matrix-build-demo
