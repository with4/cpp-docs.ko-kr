---
title: "__Declspec (dllimport)을 사용 하 여 데이터 가져오기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: dllimport
dev_langs: C++
helpviewer_keywords:
- importing data [C++]
- dllimport attribute [C++], data imports
- __declspec(dllimport) keyword [C++]
- importing DLLs [C++], __declspec(dllimport)
ms.assetid: 0ae70b39-87c7-4181-8be9-e786e0db60b0
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ebbc91b9144a7fe8025a34e9c1476ab23b604c46
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="importing-data-using-declspecdllimport"></a>__declspec(dllimport)을 사용하여 데이터 가져오기
사용 하 여 데이터의 경우 **__declspec (dllimport)** 간접 참조 계층을 제거 하는 편의 항목입니다. DLL에서 데이터를 가져올 때에 여전히 가져오기 주소 테이블을 통해 검색 해야 합니다. 하기 전에 **__declspec (dllimport)**, 즉, DLL에서 내보낸 데이터에 액세스할 때 간접 참조 수준이 강화 해야 할 기억해 야 했습니다.  
  
```  
// project.h  
#ifdef _DLL   // If accessing the data from inside the DLL  
   ULONG ulDataInDll;  
  
#else         // If accessing the data from outside the DLL  
   ULONG *ulDataInDll;  
#endif  
```  
  
 데이터를 내보낼 때 다음 프로그램. DEF 파일:  
  
```  
// project.def  
LIBRARY project  
EXPORTS  
   ulDataInDll   CONSTANT  
```  
  
 및 DLL 외부 액세스:  
  
```  
if (*ulDataInDll == 0L)   
{  
   // Do stuff here  
}  
```  
  
 데이터를 표시 하는 경우 **__declspec (dllimport)**, 컴파일러 있습니다에 대 한 간접 참조 코드를 자동으로 생성 합니다. 위의 단계를 걱정할 필요가 없습니다. 앞서 설명한 것 처럼 사용 하지 않는 **__declspec (dllimport)** DLL을 빌드할 때 데이터에 대해 선언 합니다. DLL 내에서 함수 데이터 개체;에 액세스 하려면 가져오기 주소 테이블을 사용 하지 마십시오 따라서 추가 수준의 간접 참조가 있는 않아도 됩니다.  
  
 DLL에서 데이터를 자동으로 내보내려면이 선언을 사용 합니다.  
  
```  
__declspec(dllexport) ULONG ulDataInDLL;  
```  
  
## <a name="see-also"></a>참고 항목  
 [응용 프로그램으로 가져오기](../build/importing-into-an-application.md)