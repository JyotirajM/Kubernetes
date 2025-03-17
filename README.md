
<h1>🐳 Kubernetes Node.js App Deployment</h1>

<div class="badges">
    <span class="badge">Kubernetes</span>
    <span class="badge">Docker</span>
    <span class="badge">Node.js</span>
</div>

<div class="section">
    <h2>🚀 Overview</h2>
    <p>This repository contains <strong>Node.js applications</strong>, <strong>Dockerfiles</strong>, and <strong>Kubernetes manifests</strong> to demonstrate containerized app deployments on Kubernetes.</p>
</div>

<div class="section">
    <h2>📂 Folder Structure</h2>
    <pre>
.
├── db-demo-app/             # Node.js app 1
│   ├── Dockerfile
│   ├── index.html
│   ├── index.js
│   ├── package.json
├── express-demo/            # Node.js app 2
│   ├── Dockerfile
│   ├── index.js
│   ├── package.json
├── node-file-demo/          # Node.js app 3
│   ├── Dockerfile
│   ├── app.js
│   ├── public/
├── test-app/                # Node.js test app
│   ├── Dockerfile
│   ├── package-lock.json
│   ├── package.json
│   ├── src/
│   ├── public/
├── k8s/                     # Kubernetes manifests
│   ├── deployment-node-app.yml
│   ├── mongo-config.yml
│   ├── mongo-db.yml
│   ├── service-node-app.yml
└── README.md                # Project documentation
    </pre>
</div>

<div class="section">
    <h2>📋 Prerequisites</h2>
    <ul>
        <li>🐳 <a href="https://www.docker.com/">Docker</a></li>
        <li>🛠️ <a href="https://kubernetes.io/docs/tasks/tools/">Kubernetes CLI (kubectl)</a></li>
        <li>🧑‍💻 <a href="https://minikube.sigs.k8s.io/docs/">Minikube</a> (Optional for local Kubernetes)</li>
    </ul>
</div>

<div class="section">
    <h2>🛠️ Build Docker Images</h2>
    <p>Build and push Docker images for each app:</p>
    <pre>
# Build and push for db-demo-app
docker build -t your-registry/db-demo-app:latest ./db-demo-app
docker push your-registry/db-demo-app:latest
    </pre>
    <p>Repeat the steps for <code>express-demo</code>, <code>node-file-demo</code>, and <code>test-app</code>.</p>
</div>

<div class="section">
    <h2>⚙️ Deploy on Kubernetes</h2>
    <p>Apply the Kubernetes manifest files:</p>
    <pre>
# Apply manifests
kubectl apply -f k8s/mongo-config.yml
kubectl apply -f k8s/mongo-db.yml
kubectl apply -f k8s/deployment-node-app.yml
kubectl apply -f k8s/service-node-app.yml
    </pre>
</div>

<div class="section">
    <h2>🚀 Accessing the Applications</h2>
    <p>Access the applications via exposed services:</p>
    <pre>
minikube service &lt;service-name&gt;
    </pre>
    <p>Check the status of your deployments:</p>
    <pre>
kubectl get pods
kubectl get services
    </pre>
</div>

<div class="section">
    <h2>🐛 Troubleshooting</h2>
    <p>If you encounter issues, use the following commands:</p>
    <pre>
# View pod logs
kubectl logs &lt;pod-name&gt;

# Check service and pod status
kubectl get services
kubectl get pods
    </pre>
</div>

<div class="section">
    <h2>📄 License</h2>
    <p>This project is licensed under the <strong>MIT License</strong>.</p>
</div>
