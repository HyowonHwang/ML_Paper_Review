# Basics 
## Packet
* Data Unit, immutable with timestamp

```c++
MediaPipe::Adopt()
```

## Graph
 * Packet Flow between nodes like tree.
 * 보통 Pipeline 은 forward 만 주로 가능 하지만 Backward 도 가능 하다고 함

## Node
 * Packet 를 생산 하거나 소비 eg) Gst Elements 들 과 비슷하다고 본다.

## Stream
 * Graph 의 Edge 와 같이 두 Node 간의 연결
 
## Port
 * 우리가 알고 있는 Port 와 비슷한 역할 Socket -> Packet은 Port 를 타고 가야 한다.
 
# Runtime behavior
## Graph lifetime
* initialized -> started -> cancel or finished -> destroyed or restart

## Node lifetime
* Open -> Process -> End

# Calculator
* Each calculator is a node of a graph
```c++ 

Open()
Process() (repeatedly)
Close()
```

```
node {
  calculator: "SomeAudioVideoCalculator"
  input_stream: "combined_input"
  output_stream: "VIDEO:video_stream"
  output_stream: "AUDIO:0:audio_left"
  output_stream: "AUDIO:1:audio_right"
}

node {
  calculator: "SomeAudioCalculator"
  input_stream: "audio_left"
  input_stream: "audio_right"
  output_stream: "audio_energy"
}
```


## Reference
https://google.github.io/mediapipe/framework_concepts/framework_concepts.html
