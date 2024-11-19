
# Task 4

In this task, we use RISCV Core: Verilog Netlist and Testbench to perform an experiment of Functional Simulation and observe the waveforms. The following steps explain the process.

1. First create a new directory mkdir <Directory_name>
2. Inside that directory create two new files in the name of your own choice or maazm_rv32i.v and maazm_rv32i_tb.v
3. Open terminal and install iverilog and gtkwave using the following commands.

    `sudo apt install iverilog gtkwave`
4. Now clone the given github repository.

    `git clone https://github.com/vinayrayapati/rv32i`
The given repository contains the Verilog code and Testbench code of RISCV processor. Since this internship is not part of designing RISCV architecture, we use it as reference.
5. Copy the Verilog and Testbench code from the given repository to the two files you had created initially.
6. To perform simulation first move to the directory. Next copy the command given below.

`iverilog -o <Directory_name> maazm_rv32i.v maazm_rv32i_tb.v`
`./iiitb_rv32i`
7. Now a vsd file is generated and it is stored inside you directory. To view the generated waveforms, type the following commands.

`gtkwave iiitb_rv32i.vcd`

On the wave form viewer window, drag the following signals to view the output for each cycle.

`clk`

`EX_MEM_IR[31:0]`

`ID_EX_A[31:0]`

`ID_EX_B[31:0]`

`EX_MEM_ALUOUT[31:0]`

The waveform for each instruction is shown below.

1. add r1, r2, r3:
!(https://github.com/imgb2709/RISCV_Internship/blob/main/Task%204/ADD.JPG)




## Used By

This project is used by the following companies:

- Company 1
- Company 2


## Run Locally

Clone the project

```bash
  git clone https://link-to-project
```

Go to the project directory

```bash
  cd my-project
```

Install dependencies

```bash
  npm install
```

Start the server

```bash
  npm run start
```


## Lessons Learned

What did you learn while building this project? What challenges did you face and how did you overcome them?


## License

[MIT](https://choosealicense.com/licenses/mit/)


## 🛠 Skills
Javascript, HTML, CSS...


## 🔗 Links
[![portfolio](https://img.shields.io/badge/my_portfolio-000?style=for-the-badge&logo=ko-fi&logoColor=white)](https://katherineoelsner.com/)
[![linkedin](https://img.shields.io/badge/linkedin-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/)
[![twitter](https://img.shields.io/badge/twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white)](https://twitter.com/)


# Hi, I'm Katherine! 👋


## 🚀 About Me
I'm a full stack developer...


## Feedback

If you have any feedback, please reach out to us at fake@fake.com


## Features

- Light/dark mode toggle
- Live previews
- Fullscreen mode
- Cross platform


## FAQ

#### Question 1

Answer 1

#### Question 2

Answer 2


## Environment Variables

To run this project, you will need to add the following environment variables to your .env file

`API_KEY`

`ANOTHER_API_KEY`


## Documentation

[Documentation](https://linktodocumentation)


## Deployment

To deploy this project run

```bash
  npm run deploy
```


## Demo

Insert gif or link to demo

