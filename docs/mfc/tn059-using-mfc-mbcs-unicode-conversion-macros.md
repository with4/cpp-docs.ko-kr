---
title: "TN059: MFC MBCS/유니코드 변환 매크로 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.mbcs"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "변환 매크로[C++]"
  - "유니코드 변환"
  - "매크로[C++], MBCS 변환 매크로"
  - "MBCS[C++], 변환 매크로"
  - "MFCANS32.DLL"
  - "TN059"
  - "유니코드[C++], 변환 매크로"
  - "유니코드[C++], OLE 인터페이스"
ms.assetid: a2aab748-94d0-4e2f-8447-3bd07112a705
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# TN059: MFC MBCS/유니코드 변환 매크로 사용
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  다음 기술 노트는 온라인 설명서에 먼저 포함되어 있었으므로 업데이트되지 않았습니다.  따라서 일부 절차 및 항목은 만료되거나 올바르지 않을 수 있습니다.  최신 정보를 보려면 온라인 설명서 색인에서 관심 있는 항목을 검색하는 것이 좋습니다.  
  
 This note describes how to use the macros for MBCS\/Unicode conversion, which are defined in AFXPRIV.H.  These macros are most useful if your application deals directly with the OLE API or for some reason, often needs to convert between Unicode and MBCS.  
  
## 개요  
 In MFC 3.x, a special DLL was used \(MFCANS32.DLL\) to automatically convert between Unicode and MBCS when OLE interfaces were called.  This DLL was an almost transparent layer that allowed OLE applications to be written as if the OLE APIs and interfaces were MBCS, even though they are always Unicode \(except on the Macintosh\).  While this layer was convenient and allowed applications to be quickly ported from Win16 to Win32 \(MFC, Microsoft Word, Microsoft Excel, and VBA, are just some of the Microsoft applications that used this technology\), it had a sometimes significant performance hit.  For this reason, MFC 4.x does not use this DLL and instead talks directly to the Unicode OLE interfaces.  To do this, MFC needs to convert to Unicode to MBCS when making a call to an OLE interface, and often needs to convert to MBCS from Unicode when implementing an OLE interface.  In order to handle this efficiently and easily, a number of macros were created to make this conversion easier.  
  
 One of the biggest hurdles of creating such a set of macros is memory allocation.  Because the strings cannot be converted in place, new memory to hold the converted results must be allocated.  This could have been done with code similar to the following:  
  
```  
// we want to convert an MBCS string in lpszA  
int nLen = MultiByteToWideChar(CP_ACP, 0,lpszA, -1, NULL, NULL);  
LPWSTR lpszW = new WCHAR[nLen];  
MultiByteToWideChar(CP_ACP, 0,   
   lpszA, -1, lpszW, nLen);  
// use it to call OLE here  
pI->SomeFunctionThatNeedsUnicode(lpszW);  
// free the string  
delete[] lpszW;  
```  
  
 This approach as a number of problems.  The main problem is that it is a lot of code to write, test, and debug.  Something that was a simple function call, is now much more complex.  In addition, there is a significant runtime overhead in doing so.  Memory has to be allocated on the heap and freed each time a conversion is done.  Finally, the code above would need to have appropriate `#ifdefs` added for Unicode and Macintosh builds \(which don't require this conversion to take place\).  
  
 The solution we came up with is to create some macros which 1\) mask the difference between the various platforms, and 2\) use an efficient memory allocation scheme, and 3\) are easy to insert into the existing source code.  Here is an example of one of the definitions:  
  
```  
#define A2W(lpa) (\  
    ((LPCSTR)lpa == NULL) ? NULL : (\  
          _convert = (strnlen(lpa)+1),\  
        AfxA2WHelper((LPWSTR) alloca(_convert*2),   
      lpa, _convert)\  
    )\  
)  
```  
  
 Using this macro instead of the code above and things are much simpler:  
  
```  
// use it to call OLE here  
USES_CONVERSION;  
pI->SomeFunctionThatNeedsUnicode(T2OLE(lpszA));  
```  
  
 There are extra calls where conversion is necessary, but using the macros is simple and effective.  
  
 The implementation of each macro uses the \_alloca\(\) function to allocate memory from the stack instead of the heap.  Allocating memory from the stack is much faster than allocating memory on the heap, and the memory is automatically freed when the function is exited.  In addition, the macros avoid calling **MultiByteToWideChar** \(or **WideCharToMultiByte**\) more than one time.  This is done by allocating a little bit more memory than is necessary.  We know that an MBC will convert into at most one **WCHAR** and that for each **WCHAR** we will have a maximum of two MBC bytes.  By allocating a little more than necessary, but always enough to handle the conversion the second call second call to the conversion function is avoided.  The call to the helper function **AfxA2Whelper** reduces the number of argument pushes that must be done in order to perform the conversion \(this results in smaller code, than if it called **MultiByteToWideChar** directly\).  
  
 In order to for the macros to have space to store the a temporary length, it is necessary to declare a local variable called \_convert that does this in each function that uses the conversion macros.  This is done by invoking the **USES\_CONVERSION** macro as seen above in the example.  
  
 There are both generic conversion macros and OLE specific macros.  These two different macro sets are discussed below.  All of the macros reside in AFXPRIV.H.  
  
## Generic Conversion Macros  
 The generic conversion macros form the underlying mechanism.  The macro example and implementation shown in the previous section, A2W, is one such "generic" macro.  It is not related to OLE specifically.  The set of generic macros is listed below:  
  
```  
A2CW      (LPCSTR) -> (LPCWSTR)  
A2W      (LPCSTR) -> (LPWSTR)  
W2CA      (LPCWSTR) -> (LPCSTR)  
W2A      (LPCWSTR) -> (LPSTR)  
```  
  
 Besides doing text conversions, there are also macros and helper functions for converting `TEXTMETRIC`, `DEVMODE`, `BSTR`, and OLE allocated strings.  These macros are beyond the scope of this discussion – refer to AFXPRIV.H for more information on those macros.  
  
## OLE Conversion Macros  
 The OLE conversion macros are designed specifically for handling functions that expect **OLESTR** characters.  If you examine the OLE headers, you will see many references to **LPCOLESTR** and **OLECHAR**.  These types are used to refer to the type of characters used in OLE interfaces in a way that is not specific to the platform.  **OLECHAR** maps to `char` in Win16 and Macintosh platforms and **WCHAR** in Win32.  
  
 In order to keep the number of **\#ifdef** directives in the MFC code to a minimum we have a similar macro for each conversion that where OLE strings are involved.  The following macros are the most commonly used:  
  
```  
T2COLE   (LPCTSTR) -> (LPCOLESTR)  
T2OLE   (LPCTSTR) -> (LPOLESTR)  
OLE2CT   (LPCOLESTR) -> (LPCTSTR)  
OLE2T   (LPCOLESTR) -> (LPCSTR)  
```  
  
 Again, there are similar macros for doing `TEXTMETRIC`, `DEVMODE`, `BSTR`, and OLE allocated strings.  Refer to AFXPRIV.H for more information.  
  
## 기타 고려 사항  
 Do not use the macros in a tight loop.  For example, you do not want to write the following kind of code:  
  
```  
void BadIterateCode(LPCTSTR lpsz)  
{  
   USES_CONVERSION;  
   for (int ii = 0; ii < 10000; ii++)  
      pI->SomeMethod(ii, T2COLE(lpsz));  
}  
```  
  
 The code above could result in allocating megabytes of memory on the stack depending on what the contents of the string `lpsz` is\!  It also takes time to convert the string for each iteration of the loop.  Instead, move such constant conversions out of the loop:  
  
```  
void MuchBetterIterateCode(LPCTSTR lpsz)  
{  
   USES_CONVERSION;  
   LPCOLESTR lpszT = T2COLE(lpsz);  
   for (int ii = 0; ii < 10000; ii++)  
      pI->SomeMethod(ii, lpszT);  
}  
```  
  
 If the string is not constant, then encapsulate the method call into a function.  This will allow the conversion buffer to be freed each time.  예를 들면 다음과 같습니다.  
  
```  
void CallSomeMethod(int ii, LPCTSTR lpsz)  
{  
   USES_CONVERSION;  
   pI->SomeMethod(ii, T2COLE(lpsz));  
}  
  
void MuchBetterIterateCode2(LPCTSTR* lpszArray)  
{  
   for (int ii = 0; ii < 10000; ii++)  
      CallSomeMethod(ii, lpszArray[ii]);  
}  
```  
  
 Never return the result of one of the macros, unless the return value implies making a copy of the data before the return.  For example, this code is bad:  
  
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
  
 The code above could be fixed by changing the return value to something that copies the value:  
  
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
  
 The macros are easy to use and easy to insert into your code, but as you can tell from the caveats above, you need to be careful when using them.  
  
## 참고 항목  
 [번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)   
 [범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)