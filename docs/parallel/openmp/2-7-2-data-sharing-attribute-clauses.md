---
title: "2.7.2 데이터 공유 특성 절 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 47347d3c-18bd-441f-99cf-7737564c417f
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7e3fbc78792034c60c94972ca6b4ed63dfac01b2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="272-data-sharing-attribute-clauses"></a>2.7.2 데이터 공유 특성 절
여러 지시문 절 영역의 기간에 대 한 변수 공유 특성을 제어 하는 사용자가 수락 합니다. 공유 특성 절 지시문 절은 표시 되는 어휘 범위 변수에 적용 됩니다. 다음 절 중 일부만 모든 지시문에서 허용 됩니다. 특정 지시문에서 사용할 수 있는 절 목록 지시문과 함께 설명 되어 있습니다.  
  
 변수 경우 병렬 표시 되는 작업 공유 생성자가 있으면 변수는 공유 특성 절에 지정 되지 않은 경우 또는 **threadprivate** 지시문을 다음 변수 공유 됩니다. 병렬 영역의 동적 범위 내에 선언 된 정적 변수 공유 됩니다. 힙 할당 된 메모리 (예를 들어를 사용 하 여 **malloc ()** C 또는 c + + 또는 **새** c + +에서 연산자)를 공유 합니다. 그러나 (이 메모리에 대 한 포인터 가능 전용 또는 공유 합니다.) 병렬 영역의 동적 범위 내에 선언 된 자동 저장 기간이 있는 변수는 private입니다.  
  
 절은 대부분 동의 *변수 목록* 인수는 쉼표로 구분 된 목록 표시 되는 변수입니다. 변수가 참조 하는 경우 데이터 공유 특성 절에는 서식 파일에서 파생 된 형식이 다른 프로그램에서 해당 변수 참조가 가지, 동작은 정의 되지 않았습니다.  
  
 지시문 절 내에서 표시 되는 모든 변수 표시 되어야 합니다. 필요에 따라 절을 반복 될 수 있습니다 하지만 제외 하 고 둘 다에 변수를 지정할 수 있습니다 둘 이상의 절에 변수를 지정할 수 있습니다는 **firstprivate** 및 **lastprivate** 절.  
  
 다음 섹션에서는 데이터 공유 특성 절에 설명 합니다.  
  
-   **개인**, [섹션 2.7.2.1](../../parallel/openmp/2-7-2-1-private.md) 페이지 25입니다.  
  
-   **firstprivate**, [섹션 2.7.2.2](../../parallel/openmp/2-7-2-2-firstprivate.md) 26 페이지.  
  
-   **lastprivate**, [섹션 2.7.2.3](../../parallel/openmp/2-7-2-3-lastprivate.md) 페이지 27입니다.  
  
-   **공유**, [섹션 2.7.2.4](../../parallel/openmp/2-7-2-4-shared.md) 페이지 27입니다.  
  
-   **기본**, [섹션 2.7.2.5](../../parallel/openmp/2-7-2-5-default.md) 페이지 28입니다.  
  
-   **감소**, [섹션 2.7.2.6](../../parallel/openmp/2-7-2-6-reduction.md) 페이지 28입니다.  
  
-   **copyin**, [섹션 2.7.2.7](../../parallel/openmp/2-7-2-7-copyin.md) 페이지 31입니다.  
  
-   **copyprivate**, [섹션 2.7.2.8](../../parallel/openmp/2-7-2-8-copyprivate.md) 페이지 32입니다.