---
title: "명령줄 오류 D8027 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- D8027
dev_langs:
- C++
helpviewer_keywords:
- D8027
ms.assetid: f228220f-0c7f-49a6-a6e0-1f7bd4745aa6
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1bd66688dbf582bf38fb9a0a3706663db3cf145d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="command-line-error-d8027"></a>명령줄 오류 D8027
'구성 요소' 실행할 수 없습니다.  
  
 컴파일러는 지정한 컴파일러 구성 요소 또는 링커를 실행 하지 못했습니다.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>다음과 같은 가능한 원인을 확인하여 수정하려면  
  
1.  구성 요소를 로드할 메모리가 부족 합니다. NMAKE 컴파일러를 호출 하는 경우에 메이크파일 외부에서 컴파일러를 실행 합니다.  
  
2.  현재 운영 체제 구성 요소를 실행할 수 없습니다. 확인 경로 지점의 실행 파일에 운영 체제에 적합 합니다.  
  
3.  구성 요소가 손상 되었습니다. 설치 프로그램을 사용 하 여 배포 디스크에서 구성 요소를 다시 복사 합니다.  
  
4.  옵션을 잘못 지정 되었습니다. 예:  
  
    ```  
    cl /B1 file1.c  
    ```