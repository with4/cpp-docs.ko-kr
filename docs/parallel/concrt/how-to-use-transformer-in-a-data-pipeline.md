---
title: "방법: 데이터 파이프라인에서 transformer 사용 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- transformer class, example
- data pipelines, using transformer [Concurrency Runtime]
- using transformer in data pipelines [Concurrency Runtime]
ms.assetid: ca49cb3f-4dab-4b09-a9c9-d3a109ae4c29
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 76c8a50bd5a58d9fe6e4a68f05d9732e50fd04e8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-use-transformer-in-a-data-pipeline"></a>방법: 데이터 파이프라인에서 transformer 사용
이 항목에서는 사용 하는 방법을 보여 주는 기본 예제는 [concurrency:: transformer](../../parallel/concrt/reference/transformer-class.md) 데이터 파이프라인에서 클래스입니다. 이미지 처리를 수행 하는 데이터 파이프라인을 사용 하는 자세한 예제를 참조 하십시오. [연습: 이미지 처리 네트워크 만들기](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)합니다.  
  
 *데이터 파이프라인* 동시 프로그래밍의 일반적인 패턴입니다. 데이터 파이프라인은 일련의 단계로, 여기서 각 단계 작업을 수행 하 고 다음 해당 작업의 결과 다음 단계로 전달 이루어져 있습니다. `transformer` 데이터의 핵심 구성 요소는 입력된 값을 수신 하기 때문에 파이프라인 클래스 해당 값에 대해 작업을 수행 하 고 다음 사용 하도록 다른 구성 요소에 대 한 결과 생성 합니다.  
  
## <a name="example"></a>예  
 이 예에서는 다음과 같은 데이터 파이프라인을 사용 하 여 일련의 초기 입력된 값을 지정 하는 변환 수행:  
  
1.  첫 번째 단계에서는 입력 값의 절대값을 계산 합니다.  
  
2.  두 번째 단계는 해당 입력의 제곱근을 계산합니다.  
  
3.  세 번째 단계는 입력 값의 제곱을 계산합니다.  
  
4.  단계는 입력을 부정 하는 전달 합니다.  
  
5.  다섯 번째 단계는 메시지 버퍼에는 최종 결과 씁니다.  
  
 마지막으로,이 예제에서는 콘솔에 파이프라인의 결과 인쇄 합니다.  
  
 [!code-cpp[concrt-data-pipeline#1](../../parallel/concrt/codesnippet/cpp/how-to-use-transformer-in-a-data-pipeline_1.cpp)]  
  
 이 예제는 다음과 같은 출력을 생성합니다.  
  
```Output  
The result is -42.  
```  
  
 출력에서 입력된 값과 형식이 다른 값을 데이터 파이프라인의 단계에 대 한 것이 일반적입니다. 이 예제에서는 두 번째 단계는 형식의 값 `int` 입력으로 해당 값의 제곱근을 생성 하 고 (한 `double`) 출력으로 합니다.  
  
> [!NOTE]
>  이 예에서 데이터 파이프라인에 대 한 예시는 합니다. 각 변환 작업에 약간의 작업 수행, 하기 때문에 메시지 전달을 수행 하는 오버 헤드가 필요한 보다 클 수 있습니다 데이터 파이프라인을 사용할 때의 이점입니다.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 예제 코드를 복사 하 고 Visual Studio 프로젝트에 붙여 넣거나 라는 파일에 붙여 `data-pipeline.cpp` 후 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행 합니다.  
  
 **cl.exe /EHsc data-pipeline.cpp**  
  
## <a name="see-also"></a>참고 항목  
 [비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md)   
 [비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)   
 [연습: 이미지 처리 네트워크 만들기](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)

