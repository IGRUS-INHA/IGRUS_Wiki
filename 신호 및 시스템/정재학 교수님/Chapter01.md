# What is a Signal and a System?

- Signal
    - 신호는 물리적 현상에 대한 정보를 포함하는 하나 이상의 변수의 함수로 형식적으로 정의됩니다.
        
        > A signal is formally defined as a function of one or more
        variables, which contains information on the nature of physical
        phenomenon.
        > 
    - 즉, 자연 현상의 정보를 담고 있는 함수를 신호(Signal)라 합니다.
- System
    - 시스템은 공식적으로 하나 이상의 신호를 조작하여 기능을 수행하고 이를 통해 새로운 신호를 생성하는 개체로 정의됩니다.
        
        > A system is formally defined as an entity that manipulates one or more signals to accomplish a function, thereby yielding new signals.
        > 
    - 즉, 새로운 신호를 얻기 위해 input 신호를 가공하는 것을 시스템(System)이라 합니다.

# Some Interesting Systems

- 시스템의 예시는 아래와 같습니다.
    - Communication systems
    - Control systems
    - Remote sensing system
    - Biomedical system (biomedical signal processing)
    - Video systems
    - AI (Artificial Intelligent/Machine learning)
    
    > 이런 게 있구나 정도로 이해하고 넘어가면 됩니다.
    > 

# Digital Signals

- ADC(Analog to Digital Convertor)에 대해 알아봅시다.

![image](https://github.com/user-attachments/assets/0a50702d-5c2c-4618-a51e-4c444cf2df2d)

- ADC는 아날로그 신호를 입력으로 받아 디지털 신호로 바꿔주는 시스템입니다.
- ADC에서 신호는 총 3가지 상태를 가집니다.
    - Analog Signal
      
        ![image](https://github.com/user-attachments/assets/a66ea5aa-fa40-49b2-b71c-ef7da1a27c4a)

        
        - Analog Signal은 ADC로 들어오는 입력 신호입니다.
        - 시간 도메인(time domain)에서 연속적입니다.
        - Analog Signal은 x(t)로 표기합니다.
            - 관례적으로 시간 도메인의 아날로그 신호는 소문자로 표기합니다.
            - 주파수 도메인에서는 대문자로 표기한다고 하니 참고하세요.
    - Discrete-time Signal
      
        ![image](https://github.com/user-attachments/assets/87dd6451-4c93-4388-9850-9281ea4b8ea0)
        
        - Discrete-time Signal은 Analog Signal을 샘플링(Sampling)한 결과입니다.
        - Sampling은 시간 도메인에서 일정 간격으로 값들을 추출하는 작업입니다.
            - 즉, 시간 도메인에서 연속적이었던 함수를 불연속적으로 만들어주는 작업입니다.
        - Analog Signal의 모든 정보를 저장하는 것보다 일정 구간마다 값을 1개씩만 저장하는 것이 더 효율적이기 때문에 Sampling을 수행합니다.
            - Analog Signal을 Sampling 한 결과인 Discrete-time Signal은 이론상 원본 Analog Signal로 완벽하게 복원할 수 있다고 합니다.
        - Discrete-time Signal은 x[n]으로 표기합니다.
        - 신호 및 시스템 과목에서는 Analog Signal과 Discrete-time Signal까지만 다룹니다.
    - Digital Signal
        
        ![image](https://github.com/user-attachments/assets/2a933011-3b09-422a-8b55-0fd2b45d3798)
        
        - Digital Signal은 Discrete-time Signal을 Amplitude domain에서 양자화(Quantization)한 결과입니다.
        - Discrete-time Signal은 3.237582… 처럼 소수점 자리수가 무한합니다. 이러한 값을 컴퓨터에 저장하는 것은 힘들기 때문에 Quantization을 수행합니다.
        - Quantization은 3.237582… 와 같은 수치를 3.23 과 같은 근사치로 근사시키는 작업입니다.
            - 얼마나 정밀하게 근사시킬지는 설계자가 정할 수 있습니다.
                
                ![image](https://github.com/user-attachments/assets/b2d2fbc0-a527-4db1-a19a-2bfa3af35201)

        - Quantization은 수치를 근사시키는 작업이기 때문에, Quantization 시 Quantization Error가 발생합니다.
            - Sampling의 결과물인 Discrete-time Signal은 원본인 Analog Signal로 완벽하게 복원할 수 있습니다.
            - 하지만 Quantization의 결과물인 Digital Signal은 원본인 Discrete-time Signal로 완벽하게 복원할 수 없습니다.

# Signal Classification

- Deterministic/Random Signal
    - Deterministic Signal
      
      ![image](https://github.com/user-attachments/assets/c1a5b93d-9436-442a-b60c-3ba93702e9b5)
  
        - Deterministic signal은 신호가 발생하기 전에 미리 그 신호 값을 알 수 있는 신호입니다.
            > There is no uncertainty with respect to its value at any time.
            >
        - 신호 및 시스템 과목에서는 Random signal은 다루지 않고 Deterministic signal만 다룹니다.
    - Random Signal
      
        ![image](https://github.com/user-attachments/assets/11c9baae-3479-4791-96f9-615f676eaf0f)
 
        - Random signal은 신호가 실제로 발생하기 전까지 그 신호 값을 예측할 수 없는 신호입니다.
            > There is uncertainty before its actual occurrence.
        - Deterministic signal 에 노이즈가 섞이면 Random signal이 될 수 있습니다.
- Periodic/Aperiodic(Non-periodic) Signal
    - Periodic Signal

      ![image](https://github.com/user-attachments/assets/be3fb9e6-c6d0-42a7-a417-8c1640c280df)
      
        - Periodic signal 은 주기를 갖는 신호입니다.
        - Periodic signal 함수는 아래 조건을 만족합니다.
            - x(t) = x(t + T) for all t
                - 이때 Fundamental frequency 는 1/T, Angular frequency 는 2π/T 입니다.
    - Aperiodic Signal
      
        ![image](https://github.com/user-attachments/assets/e00be867-4999-4851-af5d-a36401b33f6f)
 
        - Aperiodic signal 은 주기를 갖지 않는 신호입니다.
- Energy/Power Signal
    - Energy Signal
      - 구간 (a,b) 사이의 에너지 정의는 다음 식과 같습니다.
        - $E = \int_{a}^{b}{\left\vert x(t) \right\vert^{2} dt}$
    - Power Signal
- Continuous/Discrete Signal
