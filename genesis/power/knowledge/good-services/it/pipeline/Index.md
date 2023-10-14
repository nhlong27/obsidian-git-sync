[#index]

![[DevelopmentPipeline.excalidraw]]
- plan: (Jira) 
- code: 
	- (dev server)
	- VCS: git - host: github 
	- IDE/CE: VSCode 
		- -> linter: ESlint + formatter: Prettier + task runner 
	- Packet manager: npm 
- build: 
	- Bundler: files + dependencies + assets: Webpack, *Vite, ESbuild (transpiling, minification), Rollup (bundling) 
		- -> optimize: tree shaking, minification, code splitting + loaders 
	- Transpiler: Babel, ESbuild 
- test 
	- unit: jest, react-testing-library 
	- e2e: playwright, cypress, selenium, pw
		- https://www.reddit.com/r/QualityAssurance/comments/srhafv/cypress_vs_playwright/hwsa7pu/?utm_source=share&utm_medium=web3x&utm_name=web3xcss&utm_term=1&utm_content=share_button 
- release 
	- automation: Github Actions, Jenkins 
- deploy 
	- IaaS: EC2 
		- https://www.reddit.com/r/aws/comments/10hmnh0/comment/j59ydyq/?utm_source=share&utm_medium=web2x&context=3
		- https://www.reddit.com/r/aws/comments/10hmnh0/comment/j5chy5p/?utm_source=share&utm_medium=web2x&context=3
	- PaaS: S3, CDN 
		- https://serverless.pub/s3-or-dynamodb/
	- CaaS: Fargate 
	- FaaS/Serverless: Lambda, Vercel serverless funcs 
- operate 
	- IaC: provision, manage: terraform, ansible, AWS cloudformation 
	- Container orchestration: ECS, EKS, Kurbenetes 
	- service mesh
	- artifact  management: Artifactory
- monitor +  logs management: Elastic stack (Kibana)
		- instrumentation
		- telemetry/application monitoring: datadog
		- infrastructure monitoring: prometheus + grafana
    