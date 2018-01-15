---
title: "포인터 증가 및 감소 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- incrementing pointers
- MBCS [C++], pointers
- pointers [C++], multibyte characters
- decrementing pointers
ms.assetid: 0872b4a0-e2bd-4004-8319-070efb76f2fd
caps.latest.revision: "7"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e9eccf65f091c8c5c273f6a65cb7e81b0d386afa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="incrementing-and-decrementing-pointers"></a>포인터 증가 및 감소
다음 팁을 사용 합니다.  
  
-   선행 바이트 후행 바이트가 아니라를 가리킵니다. 후행 바이트에 대 한 포인터를 일반적으로 안전 하지 않습니다. 일반적으로 안전 하 게 역방향 보다 앞으로 검색 한 문자열은입니다.  
  
-   포인터 증가/감소 함수 및 매크로 한 문자씩 이동 하는 사용할 수 있습니다.  
  
    ```  
    sz1++;  
    ```  
  
     다음과 같이 됩니다.  
  
    ```  
    sz1 = _mbsinc( sz1 );  
    ```  
  
     `_mbsinc` 및 `_mbsdec` 함수 올바르게 증가 또는 감소 `character` 문자 크기에 관계 없이 단위입니다.  
  
-   감소를 다음과 같이 문자열의 머리에 대 한 포인터가 필요합니다.  
  
    ```  
    sz2--;  
    ```  
  
     다음과 같이 됩니다.  
  
    ```  
    sz2 = _mbsdec( sz2Head, sz2 );  
    ```  
  
     문자열에 유효한 문자로 head 포인터 또는 수 있도록 합니다.  
  
    ```  
    sz2Head < sz2  
    ```  
  
     유효한 선행 바이트에 대 한 포인터를 있어야 합니다.  
  
-   에 대 한 빠른 호출 이전 문자에 대 한 포인터를 유지 하려는 경우도 `_mbsdec`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MBCS 프로그래밍 팁](../text/mbcs-programming-tips.md)   
 [바이트 인덱스](../text/byte-indices.md)