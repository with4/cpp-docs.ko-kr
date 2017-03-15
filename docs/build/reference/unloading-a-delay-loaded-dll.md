---
title: "지연 로드된 DLL 언로드 | Microsoft Docs"
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
  - "__FUnloadDelayLoadedDLL2"
  - "지연 DLL 로드, 언로드"
ms.assetid: 6463bc71-020e-4aff-a4ca-90360411c54e
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 지연 로드된 DLL 언로드
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

기본적으로 제공되는 지연 로드 도우미는 지연 로드 설명자에 포인터가 있는지와 pUnloadIAT 필드에 원본 IAT\(가져오기 주소 테이블\)의 복사본이 있는지 여부를 확인합니다.  포인터 및 복사본이 있는 경우 도우미는 포인터를 가져오기 지연 설명자에 목록으로 저장합니다.  이렇게 하면 도우미 함수가 이름으로 DLL을 찾을 수 있으므로 해당 DLL을 명시적으로 언로드할 수 있게 됩니다.  
  
 다음은 지연 로드된 DLL을 명시적으로 언로드하는 데 사용되는 관련 구조체 및 함수입니다.  
  
```  
//  
// Unload support from delayimp.h  
//  
  
// routine definition; takes a pointer to a name to unload  
  
ExternC  
BOOL WINAPI  
__FUnloadDelayLoadedDLL2(LPCSTR szDll);  
  
// structure definitions for the list of unload records  
typedef struct UnloadInfo * PUnloadInfo;  
typedef struct UnloadInfo {  
    PUnloadInfo     puiNext;  
    PCImgDelayDescr pidd;  
    } UnloadInfo;  
  
// from delayhlp.cpp  
// the default delay load helper places the unloadinfo records in the   
// list headed by the following pointer.  
ExternC  
PUnloadInfo __puiHead;  
```  
  
 UnloadInfo 구조체는 **LocalAlloc** 및 **LocalFree** 구현을 각각 **new** 연산자와 **delete** 연산자로 사용하는 C\+\+ 클래스로 구현되었습니다.  이 옵션은 \_\_puiHead를 목록의 헤드로 사용하는 표준 링크 목록으로 유지됩니다.  
  
 \_\_FUnloadDelayLoadedDLL을 호출하면 이 함수는 로드된 DLL의 목록에서 사용자가 지정한 이름을 찾습니다. 이 경우 정확히 일치하는 이름만 찾습니다.  이름을 찾으면 썽크 포인터를 복원하기 위해 pUnloadIAT의 IAT 복사본이 실행 중인 IAT의 맨 위에 복사되고 **FreeLibrary**를 사용하여 라이브러리가 해제되며 일치하는 **UnloadInfo** 레코드의 링크가 목록에서 끊겨 레코드가 삭제된 다음 TRUE가 반환됩니다.  
  
 \_\_FUnloadDelayLoadedDLL2 함수의 인수는 대\/소문자를 구분합니다.  예를 들어, 다음과 같이 지정합니다.  
  
```  
__FUnloadDelayLoadedDLL2("user32.DLL");  
```  
  
 다음은 잘못 지정한 경우입니다.  
  
```  
__FUnloadDelayLoadedDLL2("User32.DLL");.  
```  
  
## 참고 항목  
 [Understanding the Helper Function](http://msdn.microsoft.com/ko-kr/6279c12c-d908-4967-b0b3-cabfc3e91d3d)