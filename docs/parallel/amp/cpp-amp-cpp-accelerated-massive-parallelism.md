---
title: "C++ AMP(C++ Accelerated Massive Parallelism) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C++ Accelerated Massive Parallelism, 시작"
  - "C++ AMP(C++ Accelerated Massive Parallelism 참조)"
ms.assetid: e27824cb-3167-409b-8c3f-a0e476d8f349
caps.latest.revision: 22
caps.handback.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C++ AMP(C++ Accelerated Massive Parallelism)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

C\+\+ AMP\(C\+\+가속 대규모 병렬\)는 개별 그래픽 카드의 그래픽 처리 장치\(GPU\)로 평소에 존재하는 데이터 병렬 하드웨어를 활용하여 C\+\+코드의 실행 속도를 높여 줍니다.  C\+\+ AMP 프로그래밍 모델은 다차원 배열, 인덱싱, 메모리 전송 및 바둑판식 배열을 지원합니다.  또한 수학 함수 라이브러리도 포함합니다.  C\+\+ AMP 언어 확장을 사용하여 CPU에서 GPU로, 또는 그 반대로 데이터를 이동하는 방식을 제어할 수 있습니다.  
  
## 관련 항목  
  
|제목|설명|  
|--------|--------|  
|[C\+\+ AMP 개요](../../parallel/amp/cpp-amp-overview.md)|C\+\+ AMP와 수학 라이브러리의 주요 기능에 대해 설명합니다.|  
|[람다, 함수 개체 및 제한 함수 사용](../../parallel/amp/using-lambdas-function-objects-and-restricted-functions.md)|[parallel\_for\_each](../Topic/parallel_for_each%20Function%20\(C++%20AMP\).md) 메서드에 대한 호출로 람다 식, 함수 개체 및 제한 기능 사용 방법을 설명합니다.|  
|[타일 사용](../../parallel/amp/using-tiles.md)|타일을 사용하여 C\+\+ AMP 코드 속도를 단축하는 방법에 대해 설명합니다.|  
|[accelerator 및 accelerator\_view 개체 사용](../../parallel/amp/using-accelerator-and-accelerator-view-objects.md)|액셀러레이터를 사용하여 GPU에서 코드 실행을 사용자 지정하는 방법을 설명합니다.|  
|[Windows 스토어 응용 프로그램에서 C\+\+ AMP 사용](../../parallel/amp/using-cpp-amp-in-windows-store-apps.md)|Windows 런타임 형식을 사용하는 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 앱에서 C\+\+ AMP를 사용하는 방법을 설명합니다.|  
|[그래픽\(C\+\+ AMP\)](../../parallel/amp/graphics-cpp-amp.md)|C\+\+ AMP 그래픽 라이브러리를 사용하는 방법에 대해 설명합니다.|  
|[연습: 매트릭스 곱](../../parallel/amp/walkthrough-matrix-multiplication.md)|C\+\+ AMP 코드 및 타일링을 사용하여 매트릭스 곱하기를 보여줍니다.|  
|[연습: C\+\+ AMP 응용 프로그램 디버깅](../../parallel/amp/walkthrough-debugging-a-cpp-amp-application.md)|큰 정수 배열을 정리하기 위한 병렬 영역 감소를 사용하는 응용 프로그램을 만들고 디버깅하는 방법을 설명합니다.|  
  
## 참고 항목  
 [참조\(C\+\+ AMP\)](../../parallel/amp/reference/reference-cpp-amp.md)  
  
 [tile\_static 키워드](../../cpp/tile-static-keyword.md)  
  
 [restrict \(C\+\+ AMP\)](../../cpp/restrict-cpp-amp.md)  
  
## 기타 리소스  
 [네이티브 코드 블로그의 병렬 프로그래밍](http://go.microsoft.com/fwlink/p/?LinkId=238472)  
  
 [다운로드용 C\+\+ AMP 샘플 프로젝트](http://go.microsoft.com/fwlink/p/?LinkId=248508)  
  
 [동시성 시각화 도우미를 이용한 C\+\+ AMP 코드 분석](http://go.microsoft.com/fwlink/?LinkID=253987&clcid=0x409)