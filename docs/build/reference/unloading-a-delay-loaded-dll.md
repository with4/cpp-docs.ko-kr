---
title: "지연 로드 된 DLL 언로드 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- __FUnloadDelayLoadedDLL2
- delayed loading of DLLs, unloading
ms.assetid: 6463bc71-020e-4aff-a4ca-90360411c54e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8b47969da4c560f28c07ac09caef83873e362ddc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="unloading-a-delay-loaded-dll"></a>지연 로드된 DLL 언로드
기본적으로 제공 되는 지연 로드 도우미 지연 로드 설명자는 포인터가 되 고 원래 가져오기 주소 테이블 (IAT)의 사본을 pUnloadIAT 필드에 있어야 하는 경우를 확인 합니다. 이 경우은 가져오기 지연 설명자를 목록에 대 한 포인터를 저장 합니다. 이렇게 하면 DLL을 찾을 해당 DLL의 명시적 언로드를 지원 하기 위해 이름별 도우미 함수입니다.  
  
 다음은 연결 된 구조 및 지연 로드 된 DLL의 명시적 언로드에 대 한 함수입니다.  
  
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
  
 사용 하는 c + + 클래스를 사용 하 여 UnloadInfo 구조는 구현 **LocalAlloc** 및 **LocalFree** 해당 연산자로 구현 **새** and 연산자  **삭제** 각각. 이 옵션은 목록으로 __puiHead를 사용 하는 표준 연결 된 목록에 유지 됩니다.  
  
 호출 __FUnloadDelayLoadedDLL 이름을 찾으려고 시도 합니다 (정확히 일치 하는 필수)는 로드 된 Dll 목록에 제공 합니다. 발견 pUnloadIAT의 IAT의 복사본은 복사로 해제 하는 라이브러리 썽크 포인터를 복원 하려면 실행 중인 IAT의 위에 **FreeLibrary**, 일치 하는 **UnloadInfo** 레코드는에서 연결을 끊었습니다. 목록 삭제 된 및 TRUE 반환 됩니다.  
  
 함수 __FUnloadDelayLoadedDLL2 하 인수는 대/소문자 구분입니다. 예를 들어 사용자 지정 합니다.  
  
```  
__FUnloadDelayLoadedDLL2("user32.DLL");  
```  
  
 및 not을 추가 합니다.  
  
```  
__FUnloadDelayLoadedDLL2("User32.DLL");.  
```  
  
## <a name="see-also"></a>참고 항목  
 [도우미 함수 이해](understanding-the-helper-function.md)