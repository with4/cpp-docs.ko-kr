---
title: "호출 규칙, 매개 변수, 반환 형식 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "호출 규칙, 도우미 함수"
  - "도우미 함수, 호출 규칙"
  - "도우미 함수, 반환 형식"
ms.assetid: 0ffa4558-6005-4803-be95-7a8ec8837660
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 호출 규칙, 매개 변수, 반환 형식
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

도우미 루틴의 프로토타입은 다음과 같습니다.  
  
```  
FARPROC WINAPI __delayLoadHelper2(   
   PCImgDelayDescr pidd,  
   FARPROC * ppfnIATEntry  
);  
```  
  
 다음은 각 문자에 대한 설명입니다.  
  
 `pidd`  
 다양한 가져오기 관련 데이터의 오프셋, 바인딩 정보에 대한 타임스탬프 및 설명자 콘텐츠에 대한 추가 정보를 제공하는 특성 집합이 포함된 `ImgDelayDescr`\(delayimp.h 참조\)에 대한 `const` 포인터입니다.  현재 설명자의 주소가 상대 가상 주소\(가상 주소의 반대\)임을 나타내는 `dlattrRva` 특성만 있습니다.  
  
 `PCImgDelayDescr` 구조 정의는 [구조체 및 상수 정의](../../build/reference/structure-and-constant-definitions.md)를 참조하세요.  
  
 `ppfnIATEntry`  
 가져온 함수의 주소로 업데이트되는 지연 로드된 IAT\(가져오기 주소 테이블\)의 슬롯 포인터입니다.  도우미 루틴은 이 위치에 반환할 값과 동일한 값을 저장해야 합니다.  
  
## 예상 반환 값  
 함수에 성공하면 가져온 함수의 주소가 반환됩니다.  
  
 함수에 실패하면 예외가 발생하고 0이 반환됩니다.  다음과 같은 3가지 형식의 예외가 발생할 수 있습니다.  
  
-   잘못된 매개 변수. `pidd`의 특성을 제대로 지정하지 않으면 발생합니다.  
  
-   지정된 DLL에서 실패한 `LoadLibrary`  
  
-   `GetProcAddress`의 실패  
  
 이러한 예외를 처리하는 것은 사용자의 책임입니다.  
  
## 설명  
 도우미 함수의 호출 규칙은 `__stdcall`입니다.  반환 값의 형식이 관련 없으므로 FARPROC가 사용됩니다.  이 함수에는 C 링크가 있습니다.  
  
 도우미 루틴을 알림 후크로 사용하지 않으려는 경우에는 지연 로드 도우미의 반환 값을 전달된 함수 포인터 위치에 저장해야 합니다.  이러한 경우 사용자 코드가 반환할 적절한 함수 포인터 찾기를 담당합니다.  그러면 링커가 생성한 썽크 코드가 해당 반환 값을 가져오기의 실제 대상으로 인식하여 해당 대상으로 직접 이동합니다.  
  
## 샘플  
 다음 코드는 간단한 후크 함수를 구현하는 방법을 보여줍니다.  
  
```  
FARPROC WINAPI delayHook(unsigned dliNotify, PDelayLoadInfo pdli)  
{  
    switch (dliNotify) {  
        case dliStartProcessing :  
  
            // If you want to return control to the helper, return 0.  
            // Otherwise, return a pointer to a FARPROC helper function  
            // that will be used instead, thereby bypassing the rest   
            // of the helper.  
  
            break;  
  
        case dliNotePreLoadLibrary :  
  
            // If you want to return control to the helper, return 0.  
            // Otherwise, return your own HMODULE to be used by the   
            // helper instead of having it call LoadLibrary itself.  
  
            break;  
  
        case dliNotePreGetProcAddress :  
  
            // If you want to return control to the helper, return 0.  
            // If you choose you may supply your own FARPROC function   
            // address and bypass the helper's call to GetProcAddress.  
  
            break;  
  
        case dliFailLoadLib :   
  
            // LoadLibrary failed.  
            // If you don't want to handle this failure yourself, return 0.  
            // In this case the helper will raise an exception   
            // (ERROR_MOD_NOT_FOUND) and exit.  
            // If you want to handle the failure by loading an alternate   
            // DLL (for example), then return the HMODULE for   
            // the alternate DLL. The helper will continue execution with   
            // this alternate DLL and attempt to find the  
            // requested entrypoint via GetProcAddress.  
  
            break;  
  
        case dliFailGetProc :  
  
            // GetProcAddress failed.  
            // If you don't want to handle this failure yourself, return 0.  
            // In this case the helper will raise an exception   
            // (ERROR_PROC_NOT_FOUND) and exit.  
            // If you choose you may handle the failure by returning   
            // an alternate FARPROC function address.  
  
            break;  
  
        case dliNoteEndProcessing :   
  
            // This notification is called after all processing is done.   
            // There is no opportunity for modifying the helper's behavior  
            // at this point except by longjmp()/throw()/RaiseException.   
            // No return value is processed.  
  
            break;  
  
        default :  
  
            return NULL;  
    }  
  
    return NULL;  
}  
  
/*   
and then at global scope somewhere  
PfnDliHook __pfnDliNotifyHook2 = delayHook;  
*/  
```  
  
## 참고 항목  
 [도우미 함수 이해](../../build/reference/understanding-the-helper-function.md)