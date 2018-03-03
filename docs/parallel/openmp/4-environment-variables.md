---
title: "4. 환경 변수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 4ec7ed81-e9ca-46a1-84f8-8f9ce4587346
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cef1bac78afbcc8b852c3bd42e0904e1963137c8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="4-environment-variables"></a>4. 환경 변수
OpenMP C 및 c + + API 환경 변수 (또는 해당 하는 플랫폼 특정 메커니즘)이이 장에서 설명 하는 병렬 코드의 실행을 제어 합니다.  환경 변수의 이름은 대문자 여야 합니다. 할당 된 값이 대/소문자 구분 하 고 선행 및 후행 공백은 있을 수 있습니다.  프로그램 시작 후 값의 수정 사항은 무시 됩니다.  
  
 환경 변수는 다음과 같습니다.  
  
-   **OMP_SCHEDULE** 런타임에 일정 유형 및 청크 크기를 설정 합니다.  
  
-   **OMP_NUM_THREADS** 실행 하는 동안 사용할 스레드 수를 설정 합니다.  
  
-   **OMP_DYNAMIC** 하거나 스레드 수의 동적 조정을 해제 합니다.  
  
-   **OMP_NESTED** 하거나 중첩 된 병렬 처리를 해제 합니다.  
  
 이 장의의 예제만 C Unix 셸 (csh) 환경에서 이러한 변수를 설정 하는 방법을 보여 줍니다. Korn에서 셸 및 DOS 환경 작업은와 마찬가지로 다음과 같습니다.  
  
 csh:  
 setenv OMP_SCHEDULE "동적"  
  
 ksh:  
 OMP_SCHEDULE 내보내기 = "동적"  
  
 DOS:  
 OMP_SCHEDULE 설정 = "동적"