graph LR;
	
  start(Start Here) --> GP(General Purpose);
  GP --> Mac[Mac: Apple Mac Mini]
  GP --> T1:::deprecated
  GP --> M1:::deprecated
  GP --> M3:::deprecated
  GP --> M2:::deprecated
  M1 --> T2[T2: Burstable]
  T1 --> T2
  T2 --> T3a[T3a: AMD EPYC 7000]
  T2 --> T3[T3: Intel Xeon Platinum]
  T3a --> T4g[ T4g: AWS Graviton2]
  T3 --> T4g
  GP --> A1[A1: AWS Graviton]
  GP --> M4[M4: Intel Xeon]
  M4 --> M5[M5: Intel Xeon Platinum 8175M]
  M5 --- M5d[M5d: Instance storage]:::SSD
  M1 --> M5
  M3 --> M5
  M4 --> M5a[M5a: AMD EPYC 7000]
  M5a --- M5ad[M5ad: Instance storage]:::SSD
  M4 --> M5n[M5n: High network bandwidth]
  M5n --- M5nd[M5nd: Instance storage]:::SSD
  M5n --> M5zn[M5zn: Highest Intel Xeon Scalable CPU performance and high network bandwidth]
  M5 --> M6i[M6i: 3rd gen Intel Xeon Scalable]
  M5 --> M6g[M6g: AWS Graviton2]
  M6g --- M6gd[M6gd: Instance storage]:::SSD


  start --> CO(Compute Optimized)
  CO --> C4[C4: Intel Xeon E5 2666 v3]
  CO --> C1:::deprecated
  CO --> C2:::deprecated
  CO --> C3:::deprecated
  C4 --> C5[C5: Intel Xeon-series]
  C5 --- C5d[C5d: Instance storage]:::SSD
  C1 --> C5
  C3 --> C5
  C4 --> C5a[C5a: AMD EPYX 7002]
  C5a --- C5ad[C5ad: Instance storage]:::SSD
  C4 --> C5n[C5n: High network bandwidth]
  C5 --> C6g[C6g: AWS Graviton2] 
  C6g --- C6gd[C6gd: Instance storage]:::SSD
  C5n --> C6gn[C6gn: AWS Graviton2, High network bandwidth]
  
  start --> MO(Memory Optimized)
  MO --> z1d[z1d: Intel Xeon Scalable high frequency]:::SSD
  MO --> highmem[High Memory u-Ntb1: for SAP HANA]
  MO --> X1[X1: Intel Xeon E7-8880 v3]
  X1 --> X1e[X1e: Intel Xeon E7-8880 v3, higher memory options than X1]
  X1 --> X2gd[X2gd: AWS Graviton2]
  MO --> R3:::deprecated
  MO --> CR1:::deprecated
  R3 --> R4[R4: Intel Xeon E5-2686 v4]
  M2 --> R4
  CR1 --> R4
  R4 --> R5[R5: Intel Xeon Platinum 8000]
  R5 --- R5d[R5d: Instance storage]:::SSD
  R4 --> R5a[R5a: AMD EPYC 7000]
  R5a --- R5ad[R5ad: Instance storage]:::SSD
  R4 --> R5b[R5b: EBS-optimized]
  R4 --> R5n[R5n: High network bandwidth]
  R5n --- R5dn[R5dn: Instance storage]:::SSD
  R5 --> R6g[R6g: AWS Graviton2]
  R6g ---R6gd[R6gd: Instance storage]:::SSD
  
  start --> AC(Accelerated Computing)
  AC --> P2[P2: NVIDIA K80 GPU]
  P2 --> P3[P3: NVIDIA Tesla V100 GPU]
  P3 --- P3dn[P3dn: Instance storage]:::SSD
  P3 --> P4d[P4d: NVIDIA A100 Tensor Core GPU]:::SSD
  AC --> Inf1[Inf1: AWS Inferentia]
  AC --> G2:::deprecated
  G2 --> G3[G3: NVIDIA Tesla M60 GPU, graphic-intensive]
  G3 --> G4ad[G4ad: AMD EPYC]:::SSD
  G3 --> G4dn[G4dn: High network bandwidth]:::SSD
  AC --> F1[F1: FPGA]
  AC --> VT1[VT1: video transcoding accelerator card]
  
  start --> SO(Storage Optimized)
  SO --> HS1:::deprecated
  I2 --> I3[I3:: High IOPS]
  SO --> I2:::deprecated
  I3 --> I3en[I3en: High network bandwidth]
  SO --> D2[D2: HDD]
  HS1 --> D2
  D2 --> D3[D3: HDD]
  D3 --> D3en[D3en: High network bandwidth]
  SO --> H1[H1: HDD]

  classDef GPC fill:lightgreen;
  class GP,A1,M1,M2,M3,M4,M5,M5a,M5n,M5zn,M6g,M6i,Mac,T1,T2,T3,T3a,T4,M5,M5a,M5ad,M5d,M5n,M5nd,M6g,M6gd GPC; 

  classDef COC fill:lightblue;
  class CO,C1,C2,C3,C4,C5,C5a,C5ad,C5d,C5n,C6g,C6gd,C6gn COC;

  classDef MOC fill: cyan;
  class MO,CR1,R3,R4,R5,R5a,R5ad,R5b,R5d,R5dn,R5n,R6g,R6gd,X1,X1e,X2gd,highmem,z1d MOC;
   
  classDef ACC fill: pink;
  class AC,F1,G2,G3,G4ad,G4dn,Inf1,P2,P3dn,P3,P4d,VT1 ACC

  classDef SOC fill: yellow;
  class SO,D2,D3,D3en,H1,HS1,I2,I3,I3en SOC;

  classDef PrevGen opacity:40%,stroke-dasharray:5 5; 
  class T1,M1,M2,M3,C1,C2,C3,R3,CR1,G2,HS1,I2 PrevGen
