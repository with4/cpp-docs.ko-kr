---
title: "방법: 데이터 파이프라인에서 transformer 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "transformer 클래스, 예제"
  - "데이터 파이프라인, transformer 사용[동시성 런타임]"
  - "데이터 파이프라인에서 transformer 사용[동시성 런타임]"
ms.assetid: ca49cb3f-4dab-4b09-a9c9-d3a109ae4c29
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# 방법: 데이터 파이프라인에서 transformer 사용
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 항목에는 데이터 파이프라인에서 [concurrency::transformer](../../parallel/concrt/reference/transformer-class.md) 클래스를 사용하는 방법을 보여 주는 기본 예제가 포함되어 있습니다.  데이터 파이프라인을 사용하여 이미지 처리를 수행하는 자세한 예제를 보려면 [연습: 이미지 처리 네트워크 만들기](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)를 참조하십시오.  
  
 *데이터 파이프라인*은 동시 프로그래밍에서 일반적인 패턴입니다.  데이터 파이프라인은 일련의 단계로 구성되는데, 각 단계에서는 작업을 수행한 후 해당 작업의 결과를 다음 단계로 전달합니다.  `transformer` 클래스는 입력 값을 받고 해당 값에 대한 작업을 수행한 후 다른 구성 요소에서 사용할 수 있도록 결과를 생성하므로 데이터 파이프라인의 핵심 구성 요소입니다.  
  
## 예제  
 이 예제에서는 초기 입력 값이 제공된 경우 다음과 같은 데이터 파이프라인을 사용하여 일련의 변환을 수행합니다.  
  
1.  첫 번째 단계에서는 입력 값의 절대값을 계산합니다.  
  
2.  두 번째 단계에서는 입력 값의 제곱근을 계산합니다.  
  
3.  세 번째 단계에서는 입력 값의 제곱을 계산합니다.  
  
4.  네 번째 단계에서는 입력 값을 음수로 만듭니다.  
  
5.  다섯 번째 단계에서는 최종 결과를 메시지 버퍼에 씁니다.  
  
 마지막으로 이 예제에서는 파이프라인 결과를 콘솔에 출력합니다.  
  
 [!code-cpp[concrt-data-pipeline#1](../../parallel/concrt/codesnippet/CPP/how-to-use-transformer-in-a-data-pipeline_1.cpp)]  
  
 이 예제는 다음과 같은 출력을 생성합니다.  
  
  **결과는 \-42 입니다.** 데이터 파이프라인의 단계에서는 입력 값과 형식이 다른 값을 출력하는 것이 일반적입니다.  이 예제의 경우 두 번째 단계에서 `int` 형식의 값을 입력 값으로 사용하고 이 값의 제곱근\(`double`\)을 출력 값으로 생성합니다.  
  
> [!NOTE]
>  이 예제의 데이터 파이프라인은 설명을 위한 것입니다.  각 변환 작업\(operation\)은 작업\(work\)을 거의 수행하지 않으므로 메시지 전달을 수행하는 데 필요한 오버헤드가 데이터 파이프라인을 사용하여 얻는 이점보다 클 수 있습니다.  
  
## 코드 컴파일  
 예제 코드를 복사하여 Visual Studio 프로젝트 또는 `data-pipeline.cpp` 파일에 붙여넣고Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.  
  
 **cl.exe \/EHsc data\-pipeline.cpp**  
  
## 참고 항목  
 [비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md)   
 [비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)   
 [연습: 이미지 처리 네트워크 만들기](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)