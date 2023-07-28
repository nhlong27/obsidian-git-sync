
![[PhysicalArchitectureModel.excalidraw]]
Hardware
	Core concepts
		CPU (control unit + arithmetic logic unit + registers) https://www.youtube.com/watch?v=4rLW7zg21gI
			Thread, Process, physical/logical Core, hyper-threading/Multi-threading, parallel operations, concurrent operations, processor vs micro processor https://qr.ae/pyTEhM			![[Pasted image 20230503073757.png]]
			![[Pasted image 20230503074948.png]]
			![[Pasted image 20230503074537.png]]
			Examples
				Intel Core i5, i7 (i7-9750H 2.60GHz x64, 64-bit OS) Xeon
				AMD Ryzen 5, 7
				ARM for mobile -> Apple Silicon, SoCs
				NVIDA Tegra
			--------------------------------------------------
		GPU frame rate --- Display refresh rate
			microprocessor + Memory VRAM (specialized for graphics =/= CPU general purposes)  
			Examples
				NVIDIA GeForce RTX, GTX, Quadro, Tesla (GTX 1650 4GB GDDR5)
				AMD Radeon RX, Pro
		RAM (Primary memory)
			8, 16GB (8GB DDR4 2666MHz,1 khe cắm), frequency/cycles per second + 64 bit data width -> (DDR) 128 bits 
		Storage (Secondary memory)
			SSD (512GB SSD M.2 2242 NVMe)
			HDD
			Hybrid (SSD as cache)	
			![[Pasted image 20230502071344.png]]
	Inputs & Outputs
		Ports (2x USB 3.1, 1x USB 3.1 Type-C, HDMI, RJ-45)
			USB
			HDMI
			Ethernet
		OS
		*Display
			HDR
			refresh rate
			Panel type (response time, contrast, viewing angle): TN, VA, IPS

'Software'
	OS
	File system
		Fat32, exFat, ntfs
	Hypervisor
		Type 1: enterprises
			 Windows: Hyper-V
		Type 2: installed
			Oracle VM VirtualBox

OSes don't have the capability to run multiple applications *securely* on a single server
	VM
		storage
		power (cpu + ram)
		slow startup
		licenses
	Container engine
		small file size
		less power
		fast
Simulation program: controlled environment for training, testing
	flight, driving simulations
Emulator  (VM is a type of emulator) program: emulate environment, platform specific
	
	