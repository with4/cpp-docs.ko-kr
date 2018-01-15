---
title: "TN059: MFC MBCS 유니코드 변환 매크로 사용 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.mfc.mbcs
dev_langs: C++
helpviewer_keywords:
- MFCANS32.DLL
- Unicode [MFC], conversion macros
- Unicode [MFC], OLE interfaces
- conversion macros [MFC]
- converting Unicode
- MBCS [MFC], conversion macros
- macros [MFC], MBCS conversion macros
- TN059
ms.assetid: a2aab748-94d0-4e2f-8447-3bd07112a705
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 45df45fe3d06e71b33c20ecd88d3f958a5673df1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="tn059-using-mfc-mbcsunicode-conversion-macros"></a>TN059: MFC MBCS/유니코드 변환 매크로 사용
> [!NOTE]
>  다음 기술 노트는 온라인 설명서에 먼저 포함되어 있었으므로 업데이트되지 않았습니다. 따라서 일부 절차 및 항목은 만료되거나 올바르지 않을 수 있습니다. 최신 정보를 보려면 온라인 설명서 색인에서 관심 있는 항목을 검색하는 것이 좋습니다.  
  
 이 노트 AFXPRIV에 정의 된 MBCS/유니코드 변환에 대 한 매크로 사용 하는 방법을 설명 합니다. 8. 이 매크로 응용 프로그램 거래 직접 OLE api 또는 몇 가지 이유로, 종종 필요로 하는 유니코드 및 MBCS 사이 변환할 경우 가장 유용 합니다.  
  
## <a name="overview"></a>개요  
 Mfc에서 3.x에서 특별 한 DLL 되었습니다 (MFCANS32 사용. DLL) OLE 인터페이스 호출 된 경우 유니코드 및 MBCS 간에 자동으로 변환 합니다. 이 DLL을 쓰려고 하면 OLE Api 및 인터페이스 MBCS 것 처럼 유니코드 발생 하는 항상 OLE 응용 프로그램을 허용 하는 거의 투명 계층이 못했습니다 (macintosh 제외). 이 계층 편리 하 게 되는 동안 응용 프로그램을 신속 하 게 이식 Win16에서 Win32 허용 (MFC, Microsoft Word, Microsoft Excel 및 VBA에는이 기술을 사용 하는 Microsoft 응용 프로그램 중 일부가), 때로는 심각한 성능 이전의 적중 합니다. 이러한 이유로 MFC 4.x이이 DLL을 사용 하지 않는 대신 유니코드 OLE 인터페이스에 직접 설명 하 고 있습니다. 이 위해 MFC OLE 인터페이스를 호출 하는 경우 MBCS로 유니코드로 변환 하면 종종 OLE 인터페이스를 구현 하는 경우 유니코드에서 MBCS로 변환 해야 합니다. 이 쉽고 효율적으로 처리 하기 위해 다양 한 매크로가이 변환을 쉽게 수행할 수 있도록 만들어졌습니다.  
  
 이러한 매크로의 집합을 만드는 가장 큰 장애물 중 하나에 메모리 할당입니다. 위치에 문자열을 변환할 수 없습니다, 때문에 변환 된 결과를 저장할 새 메모리 할당 되어야 합니다. 이것으로 수행 하기 위해 다음과 유사한 코드:  
  
```  
// we want to convert an MBCS string in lpszA  
int nLen = MultiByteToWideChar(CP_ACP,
    0,
    lpszA, -1,
    NULL,
    NULL);

LPWSTR lpszW = new WCHAR[nLen];  
MultiByteToWideChar(CP_ACP,
    0,   
    lpszA, -1,
    lpszW,
    nLen);

// use it to call OLE here  
pI->SomeFunctionThatNeedsUnicode(lpszW);

// free the string  
delete[] lpszW;  
```  
  
 이 방법으로 여러 가지 문제를 합니다. 주요 문제는 많은 양의 코드를 작성, 테스트 및 디버그 된다는 점입니다. 간단한 함수 호출이 있는 이제 훨씬 더 복잡 합니다. 또한이 작업에 오버 헤드는 중요 한 런타임 있습니다. 힙에 할당 하 고 변환 될 때마다 해제를 메모리에 있습니다. 마지막으로, 위 코드는 해야 할 적절 한 `#ifdefs` (여기이 변환이 수행 필요 하지 않습니다) 유니코드 또는 Macintosh 빌드에 대 한 추가 되었습니다.  
  
 우리가 솔루션 1) 마스크 다양 한 플랫폼 및 2) 사용 하 여 효율적인 메모리 할당 체계의 차이 및 3)은 쉽게 기존에 삽입할 수 있는 소스 코드 일부 매크로 만드는 것입니다. 정의 중 하나는 예는 다음과 같습니다.  
  
```  
#define A2W(lpa) (\  
 ((LPCSTR)lpa == NULL) NULL : (\  
    _convert = (strnlen(lpa)+1),\  
    AfxA2WHelper((LPWSTR) alloca(_convert*2),   
    lpa,
    _convert)\)\)  
```  
  
 이 위의 코드 대신 매크로 및 작업을 사용 하 여 보다 간단 하 게 됩니다.  
  
```  
// use it to call OLE here  
USES_CONVERSION;  
pI->SomeFunctionThatNeedsUnicode(T2OLE(lpszA));
```  
  
 변환 시 문자열이 되지만 경우가 매크로 사용 하 여 간단 하 고 효율적인 추가 호출이 있습니다.  
  
 각 매크로 구현 _alloca () 함수를 사용 하 여 힙에 대신 스택에서 메모리를 할당할 수 있습니다. 스택에서 메모리를 할당 하는 보다 훨씬 힙에서 메모리를 할당 하 고 메모리는 함수가 종료 될 때 자동으로 해제 됩니다. 또한 매크로 호출을 하지 **MultiByteToWideChar** (또는 **WideCharToMultiByte**) 한 번 이상. 이 옵션은 필요한 것 보다 좀 더 많은 메모리를 할당 하 여 수행 됩니다. 회원님의 MBC 최대 하나의 변환 됩니다 **WCHAR** 있고 각각에 대해 **WCHAR** 최대 두 개의 MBC 바이트 있다고 합니다. 약 필요 하지만 항상 충분히 할당 하 여 두 번째 변환이 두 번째 호출을 처리 하는 변환 함수에 호출을 금지 합니다. 도우미 함수에 대 한 호출 **AfxA2Whelper** 는 변환을 수행 하기 위해 수행 해야 하는 인수 푸시의 수를 줄입니다 (호출 되 고 있는 경우 더 작은 코드를 보다이 인해 **MultiByteToWideChar**직접).  
  
 저장할 공간이 매크로 대 한 순서에이 변환 매크로 사용 하는 작업을 위해 각 함수는 변환 (_c) 라는 지역 변수를 선언 하는 데 필요한 임시 길이입니다. 호출 하 여 이렇게는 **따라** 예제에서 위의 예제와 같이 매크로입니다.  
  
 제네릭 변환 매크로 OLE 특정 매크로 모두 있습니다. 이러한 두 개의 다른 매크로 집합 아래 설명 되어 있습니다. 모든 매크로 AFXPRIV에 있어야합니다. 8.  
  
## <a name="generic-conversion-macros"></a>제네릭 변환 매크로  
 제네릭 변환 매크로 기본 메커니즘을 형성합니다. 매크로 예제 및 A2W, 이전 섹션에 표시 된 구현에는 "일반" 같은 단일 매크로입니다. 것 관련이 없는 OLE 특히 합니다. 제네릭 매크로의 집합은 다음과 같습니다.  
  
```  
A2CW      (LPCSTR) -> (LPCWSTR)  
A2W      (LPCSTR) -> (LPWSTR)  
W2CA      (LPCWSTR) -> (LPCSTR)  
W2A      (LPCWSTR) -> (LPSTR)  
```  
  
 텍스트 변환 수행, 외에도 있습니다 매크로 및 변환 하기 위한 도우미 함수 `TEXTMETRIC`, `DEVMODE`, `BSTR`, 및 OLE 문자열을 할당 합니다. 이 토론의 범위를 벗어나지만이 매크로-AFXPRIV를 참조 하십시오. 이러한 매크로 대 한 자세한 내용은 H입니다.  
  
## <a name="ole-conversion-macros"></a>OLE 변환 매크로  
 OLE 변환 매크로 함수에 처리 하기 위한 전용 만들어진 **OLESTR** 문자입니다. 에 대 한 많은 참조가 표시는 OLE 머리글을 검사 하면 **LPCOLESTR** 및 **OLECHAR**합니다. 이러한 형식은 플랫폼에 특정 하지 않은 방식으로 OLE 인터페이스에 사용 된 문자의 형식을 참조 하는 데 사용 됩니다. **OLECHAR** 매핑됩니다 `char` Win16 및 Macintosh 플랫폼에서 및 **WCHAR** win32에서 합니다.  
  
 개수를 유지 하기 위해 **#ifdef** MFC의 지시문 코드를 최소한으로 각 변환에 대 한 유사한 매크로 하는 OLE 문자열이 포함 되어 있습니다. 다음 매크로 가장 일반적으로 사용 됩니다.  
  
```  
T2COLE   (LPCTSTR) -> (LPCOLESTR)  
T2OLE   (LPCTSTR) -> (LPOLESTR)  
OLE2CT   (LPCOLESTR) -> (LPCTSTR)  
OLE2T   (LPCOLESTR) -> (LPCSTR)  
```  
  
 다시, 이렇게 하면 유사한 매크로 `TEXTMETRIC`, `DEVMODE`, `BSTR`, 및 OLE 문자열을 할당 합니다. AFXPRIV를 참조 하십시오. 자세한 내용은 H.  
  
## <a name="other-considerations"></a>기타 고려 사항  
 루프에서 매크로 사용 하지 마십시오. 예를 들어 다음 코드의 종류를 작성 하지 않을 수 있습니다.  
  
```  
void BadIterateCode(LPCTSTR lpsz)  
{  
    USES_CONVERSION; 
    for (int ii = 0; ii <10000; ii++)  
    pI->SomeMethod(ii, T2COLE(lpsz));

}  
```  
  
 위의 코드에서 문자열의 내용에 따라 스택에 메모리를 할당 될 수 `lpsz` 됩니다! 또한 루프의 각 반복에 대 한 문자열을 변환 하는 데 시간이 걸립니다. 이러한 상수 변환이 루프 밖으로 이동 하십시오.  
  
```  
void MuchBetterIterateCode(LPCTSTR lpsz)  
{  
    USES_CONVERSION; 
    LPCOLESTR lpszT = T2COLE(lpsz);

    for (int ii = 0; ii <10000; ii++)  
    pI->SomeMethod(ii, lpszT);

}  
```  
  
 문자열 상수 없는 경우 다음 함수에는 메서드를 캡슐화 합니다. 따라서 변환 버퍼 때마다 해제 될 수 있습니다. 예:  
  
```  
void CallSomeMethod(int ii, LPCTSTR lpsz)  
{  
    USES_CONVERSION; 
    pI->SomeMethod(ii, T2COLE(lpsz));

}  
 
void MuchBetterIterateCode2(LPCTSTR* lpszArray)  
{  
    for (int ii = 0; ii <10000; ii++)  
    CallSomeMethod(ii, lpszArray[ii]);

}  
```  
  
 반환 값 반환 하기 전에 데이터의 복사본을 만드는 것을 의미 하지 않는 한 매크로 중 하나의 결과 반환 하지 않습니다. 예를 들어이 코드는 잘못 되었습니다.  
  
```  
LPTSTR BadConvert(ISomeInterface* pI)  
{  
    USES_CONVERSION; 
    LPOLESTR lpsz = NULL;  
    pI->GetFileName(&lpsz);

 LPTSTR lpszT = OLE2T(lpsz);

    CoMemFree(lpsz);

 return lpszT; // bad! returning alloca memory  
}  
```  
  
 위의 코드 값을 복사 하는 것으로 반환 값을 변경 하 여 해결할 수 있습니다.  
  
```  
CString BetterConvert(ISomeInterface* pI)  
{  
    USES_CONVERSION; 
    LPOLESTR lpsz = NULL;  
    pI->GetFileName(&lpsz);

 LPTSTR lpszT = OLE2T(lpsz);

    CoMemFree(lpsz);

 return lpszT; // CString makes copy  
}  
```  
  
 매크로 사용 하기 편리 하며 쉽게 코드에 삽입할 수 있지만 사용할 때는 주의를 기울여야 할에서 위의 제한 사항 있음.  
  
## <a name="see-also"></a>참고 항목  
 [번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)   
 [범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)

