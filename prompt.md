## 환경 설정
- Verilator와 bender 툴을 설치해주세요.

- 'bender script' 명령을 사용하여 verilator simulation을 위한 스크립트 파일들을 scripts폴더에 만들어주세요.

- axi2per 모듈을 위한 Testbench와 AXI4 Slave RTL model를 sim/에 만들어주세요.

- 현재 시뮬레이션 구조에 맞게 src/axi4_burst_split.sv 시뮬레이션이 되도록 수정한 후 verilator로 정상적으로 동작하는지 확인해주세요.
  
- axi4_burst_split 전용 TB를 test/에 추가해서, len_limit AXI-Lite write 후 burst 분할 동작까지 기능 검증해주세요.

- scripts/verilator_sim.sh로 시뮬레이션 해주세요.

## AMD Custom IP
- src/*.sv 파일들을 AMD custom IP로 packaging할 수 있도록 wrapper 모듈을 src/*_wrapper.sv 파일로 만들어주세요. 이때, Struct 타입 port와 parameter input을 flat port로 변경해주세요.

- src/*_wrapper.sv 파일은 AMD custom IP packaging 용 wrapper 모듈이며 plat port로 변경해주세요.
  
- per2axi 모듈을 AMD custom IP로 packaging 해서 IP폴더에 만들어 주세요. 이때 systemverilog 파일은 복사하지 말고 파일 경로로 추가해주세요.

- src/axi_lite_regs.sv파일내 axi_lite_regs 모듈을 AMD custom IP로 packaging할 수 있도록 wrapper 모듈을 src/axi_lite_regs_wrapper.sv 파일로 만들어주세요.
    
## 문서화
- *.sv systemverilog 파일을 분석한 후, block diagram을 포함하여 동일 경로에 *.sv.md 마크다운 파일로 만들어주세요.

- src/*_wrapper.sv systemverilog 파일을 분석한 후, block diagram을 포함하여 동일 경로에 *.sv.md 마크다운 파일로 만들어주세요.
  
- doc/*.md 파일을 한국어로 번역한 후, 동일 경로에 *.kr.md 마크다운 파일로 만들어주세요.
  
## GIT
- Github에 PR을 생성해주세요.
- 현재 브랜치를 master와 완전히 동일하게 리셋해주세요.
- PR을 master beanch에 적용해주세요.

## 보기
- peripheral 데이터 사이즈를 PER_DATA_WIDTH로 parameter화 해주세요.
- axi2per.sv의 peripheral port를 https://github.com/chorus96/per2axi/blob/master/src/per2axi.sv peripheral port와 완벽하게 연결할 수 있도록 수정해주세요.
- PER_DATA_WIDTH=256, AXI_DATA_WIDTH=64 이고 AXI 4beat burst일때, 정상적으로 동작하는지 확인해주세요.
