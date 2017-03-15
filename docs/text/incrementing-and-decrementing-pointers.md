---
title: "포인터 증가 및 감소 | Microsoft Docs"
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
  - "포인터 감소"
  - "포인터 증가"
  - "MBCS[C++], 포인터"
  - "포인터[C++], 멀티바이트 문자"
ms.assetid: 0872b4a0-e2bd-4004-8319-070efb76f2fd
caps.latest.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 7
---
# 포인터 증가 및 감소
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음 팁을 사용하십시오.  
  
-   후행 바이트가 아니라 선행 바이트를 가리킵니다.  일반적으로 후행 바이트에 대한 포인터를 사용하는 것은 안전하지 않으며  문자열을 뒤로 검색하는 것보다 앞으로 검색하는 것이 안전합니다.  
  
-   다음과 같이 한 문자씩 이동하는 포인터 증가\/감소 함수와 매크로를 사용할 수 있습니다.  
  
    ```  
    sz1++;  
    ```  
  
     다음과 같이 됩니다.  
  
    ```  
    sz1 = _mbsinc( sz1 );  
    ```  
  
     `_mbsinc` 함수와 `_mbsdec` 함수는 문자 크기에 관계 없이 `character` 단위로 증가 또는 감소합니다.  
  
-   감소의 경우 다음과 같이 문자열 헤드에 대한 포인터를 지정해야 합니다.  
  
    ```  
    sz2--;  
    ```  
  
     다음과 같이 됩니다.  
  
    ```  
    sz2 = _mbsdec( sz2Head, sz2 );  
    ```  
  
     또는 헤드 포인터가 다음과 같이 문자열의 유효한 문자가 될 수 있습니다.  
  
    ```  
    sz2Head < sz2  
    ```  
  
     유효한 선행 바이트에 대해 포인터를 지정해야 합니다.  
  
-   `_mbsdec`를 더 빨리 호출하기 위해 이전 문자에 대한 포인터를 유지할 수도 있습니다.  
  
## 참고 항목  
 [MBCS 프로그래밍 팁](../text/mbcs-programming-tips.md)   
 [바이트 인덱스](../text/byte-indices.md)