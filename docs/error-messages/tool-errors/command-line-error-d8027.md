---
title: "명령줄 오류 D8027 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "D8027"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "D8027"
ms.assetid: f228220f-0c7f-49a6-a6e0-1f7bd4745aa6
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 명령줄 오류 D8027
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'component'을\(를\) 실행할 수 없습니다.  
  
 컴파일러가 지정한 컴파일러 구성 요소 또는 링커를 실행할 수 없습니다.  
  
### 문제 해결을 위하여 확인해 볼 수 있는 원인  
  
1.  메모리가 부족하여 구성 요소를 로드할 수 없습니다.  NMAKE가 컴파일러를 호출한 경우 메이크파일 외부에서 컴파일러를 실행합니다.  
  
2.  현재 운영 체제에서는 해당 구성 요소를 실행할 수 없습니다.  경로가 가리키고 있는 실행 파일이 운영 체제에 적절한지 확인하십시오.  
  
3.  구성 요소가 손상되었습니다.  SETUP 프로그램을 사용하여 배포 디스크에서 구성 요소를 다시 복사하십시오.  
  
4.  옵션 지정이 잘못되었습니다.  예를 들면 다음과 같습니다.  
  
    ```  
    cl /B1 file1.c  
    ```