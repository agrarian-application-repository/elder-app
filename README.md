## ELDER - AGRARIAN Project

## 1.	Testbed
Testbed 4- SEED-5G: SpaceEdge AI-Enabled Delay-Tolerant NB-IoT Platform.

## 2.	Dataset
For the lameness classification we used a custom dataset from the sheep lameness videos we gathered from our sheep farm collaborator.
For the sheep detection and pose estimation we used a pretrained model which was trained on SuperAnimal-Quadruped-80k dataset.

##  3.	Node Type
Edge, Jetson Orin

## 4.	Application Name:
ELDER

## 5.	Application Objective
The main purpose of the ELDER application is to provide a cost-effective, non-invasive, and geographically agnostic health monitoring system for small ruminants, specifically transforming the subjective, labor-intensive manual task of sheep lameness detection into an objective, automated data stream.

## 6.Use Case Description
The ELDER application provides an AI-based solution for real-time lameness detection in sheep, specifically validated on a sheep farm in Greece. The system uses edge computing to process camera data locally and then transmits only lightweight metadata (e.g. Animal ID, Lameness Score) using a Store-and-Forward mechanism over hybrid communication networks, including Sateliot's 5G NB-IoT testbed. Aligning with the AGRARIAN project, we successfully demonstrate the development of an Agricultural Decision Support System (ADSS) that utilizes IoT, Edge AI, and a Hybrid Communication Emulated infrastructure to achieve connectivity in remote agricultural areas with limited connectivity.

## 7.	Organization:
PLAIXUS PRIVATE COMPANY (PLX)

## 8.	Use instructions
A. Required Inputs  
⦁	--source (live source name zed/opencv or video path) plus the default model/checkpoint/ID files (--model config/dlclive_elder.pt, --hrnn config/hrnn_best.pth, --ids data/batch_ids.txt) so DLCLive and the HRNN processor can run with the same Elder dataset  
⦁	Optional flags for device targeting (--device, default auto), processing rate control (--skip-frames, --print-fps), TensorRT toggled (--notensorrt), auto-posting to the Agrarian endpoint (--auto-post), and inference latency tracking (--inferencetime) for the edge deployment.  
⦁	For the comprehensive docker commands and more details check the docker image readme.md  

B. Expected Outputs  
⦁	Structured TinyDB event log: every detection is written to results/results.json (and auto-posted if --auto-post),  
⦁	Console/file logs capturing FPS, errors, and pipeline start/stop into results/run.log  
⦁	Demo payloads saved under results/ (e.g. demo_events.json) that can be posted to Agrarian’s REST endpoint using tools/send_demo_events.py or the documented Docker commands  
