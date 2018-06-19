---
title: C + + AMP (c + + Accelerated Massive Parallelism) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- C++ AMP (see C++ Accelerated Massive Parallelism)
- C++ Accelerated Massive Parallelism, getting started
ms.assetid: e27824cb-3167-409b-8c3f-a0e476d8f349
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 98ae6b6a5cd24a1ea146cca7ccb30fcbdc93ae75
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33705369"
---
# <a name="c-amp-c-accelerated-massive-parallelism"></a>C++ AMP(C++ Accelerated Massive Parallelism)
데이터 병렬 하드웨어는 일반적으로 개별 그래픽 카드에 그래픽 처리 장치 GPU ()를 사용 하 여 c + + 코드의 실행을 가속화 하는 c + + AMP (c + + Accelerated Massive Parallelism). C + + AMP 프로그래밍 모델에서는 다차원 배열 인덱싱 메모리 전송 및 바둑판식으로 배열에 대 한 지원 합니다. 수치 연산 함수 라이브러리를 있습니다. C + + AMP 언어 확장을 사용 하 여 cpu에서를 GPU에 데이터는 이동 하는 방법을 제어할 수 있으며 백업할 수 있습니다.  
  
## <a name="related-topics"></a>관련 항목  
  
|제목|설명|  
|-----------|-----------------|  
|[C++ AMP 개요](../../parallel/amp/cpp-amp-overview.md)|C + + AMP 및 수학 라이브러리의 주요 기능에 설명합니다.|  
|[람다, 함수 개체 및 제한 함수 사용](../../parallel/amp/using-lambdas-function-objects-and-restricted-functions.md)|에 대 한 호출에서 람다 식, 함수 개체 및 제한 된 함수를 사용 하는 방법에 설명 된 [parallel_for_each](reference/concurrency-namespace-functions-amp.md#parallel_for_each) 메서드.|  
|[타일 사용](../../parallel/amp/using-tiles.md)|C + + AMP 코드를 가속화 하 타일을 사용 하는 방법을 설명 합니다.|  
|[accelerator 및 accelerator_view 개체 사용](../../parallel/amp/using-accelerator-and-accelerator-view-objects.md)|액셀러레이터 키를 사용 하 여 GPU에서 코드 실행을 사용자 지정 하는 방법에 설명 합니다.|  
|[UWP 앱에서 C++ AMP 사용](../../parallel/amp/using-cpp-amp-in-windows-store-apps.md)|Windows 런타임 형식을 사용 하는 유니버설 Windows 플랫폼 (UWP) 앱에서 c + + AMP를 사용 하는 방법을 설명 합니다.|  
|[그래픽(C++ AMP)](../../parallel/amp/graphics-cpp-amp.md)|C + + AMP 그래픽 라이브러리를 사용 하는 방법을 설명 합니다.|  
|[연습: 매트릭스 곱](../../parallel/amp/walkthrough-matrix-multiplication.md)|행렬 곱을 바둑판식으로 배열 및 c + + AMP를 사용 하 여 보여 줍니다.|  
|[연습: C++ AMP 응용 프로그램 디버깅](../../parallel/amp/walkthrough-debugging-a-cpp-amp-application.md)|작성 하 고 정수 대형 배열을 하자면 병렬 감소를 사용 하는 응용 프로그램을 디버깅 하는 방법에 설명 합니다.|  
  
## <a name="reference"></a>참조  
 [참조(C++ AMP)](../../parallel/amp/reference/reference-cpp-amp.md)  
  
 [tile_static 키워드](../../cpp/tile-static-keyword.md)  
  
 [restrict(C++ AMP)](../../cpp/restrict-cpp-amp.md)  
  
## <a name="other-resources"></a>기타 리소스  
 [네이티브 코드 블로그에서 병렬 프로그래밍](http://go.microsoft.com/fwlink/p/?linkid=238472)  
  
 [다운로드에 대 한 c + + AMP 샘플 프로젝트](http://go.microsoft.com/fwlink/p/?linkid=248508)  
  
 [동시성 시각화 도우미를 사용 하 여 c + + AMP 코드 분석](http://go.microsoft.com/fwlink/p/?linkid=253987&clcid=0x409)

