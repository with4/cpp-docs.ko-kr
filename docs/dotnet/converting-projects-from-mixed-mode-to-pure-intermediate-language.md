---
title: "프로젝트를 혼합 모드에서 순수 IL로 변환 | Microsoft Docs"
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
  - "intermediate language, 혼합 모드 응용 프로그램"
  - "혼합 모드 응용 프로그램"
  - "혼합 모드 응용 프로그램, intermediate language"
  - "프로젝트[C++], IL로 변환"
ms.assetid: 855f9e3c-4f09-4bfe-8eab-a45f68292be9
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 프로젝트를 혼합 모드에서 순수 IL로 변환
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

모든 Visual C\+\+ CLR 프로젝트는 기본적으로 C 런타임 라이브러리에 링크됩니다.  그 결과 네이티브 코드와 공용 언어 런타임을 대상으로 하는 코드\(관리 코드\)를 함께 사용하므로 이러한 프로젝트는 혼합 모드 응용 프로그램으로 분류됩니다.  이러한 프로젝트는 컴파일될 때 MSIL\(Microsoft intermediate language\)이라고도 하는 IL\(Intermediate Language\)로 컴파일됩니다.  
  
### 혼합 모드 응용 프로그램을 순수 IL로 변환하려면  
  
1.  다음과 같이 CRT\([C Run\-Time Libraries](../c-runtime-library/crt-library-features.md)\)에 대한 링크를 제거합니다.  
  
    1.  응용 프로그램의 진입점을 정의하는 .cpp 파일에서 진입점을 `Main()`으로 변경합니다.  `Main()`을 사용하면 프로젝트는 CRT에 링크되지 않습니다.  
  
    2.  솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **속성**을 선택하여 응용 프로그램의 속성 페이지를 엽니다.  
  
    3.  **링커**의 **고급** 프로젝트 속성 페이지에서 **진입점**을 선택한 다음 이 필드에 **Main**을 입력합니다.  
  
    4.  콘솔 응용 프로그램의 경우, **링커**의 **시스템** 프로젝트 속성 페이지에서 **하위 시스템** 필드를 선택하고 이 필드를 **콘솔\(\/SUBSYSTEM:CONSOLE\)**로 변경합니다.  
  
        > [!NOTE]
        >  Windows Forms 응용 프로그램의 경우에는 **하위 시스템** 필드가 기본적으로 **Windows\(\/SUBSYSTEM:WINDOWS\)**로 설정되어 있으므로 이 속성을 설정할 필요가 없습니다.  
  
    5.  stdafx.h에서 `#include` 문을 모두 주석으로 처리합니다.  예를 들어, 콘솔 응용 프로그램에서는 다음과 같이 합니다.  
  
        ```  
        // #include <iostream>  
        // #include <tchar.h>  
        ```  
  
         또는  
  
         예를 들어, Windows Forms 응용 프로그램에서는 다음과 같이 합니다.  
  
        ```  
        // #include <stdlib.h>  
        // #include <malloc.h>  
        // #include <memory.h>  
        // #include <tchar.h>  
        ```  
  
    6.  Windows Forms 응용 프로그램의 경우에는 Form1.cpp에서 windows.h를 참조하는 `#include` 문을 주석으로 처리합니다.  예를 들면 다음과 같습니다.  
  
        ```  
        // #include <windows.h>  
        ```  
  
2.  다음 코드를 stdafx.h에 추가합니다.  
  
    ```  
    #ifndef __FLTUSED__  
    #define __FLTUSED__  
       extern "C" __declspec(selectany) int _fltused=1;  
    #endif  
    ```  
  
3.  다음과 같이 관리되지 않는 형식을 모두 제거합니다.  
  
    1.  해당되는 경우, 관리되지 않는 형식을 [System](https://msdn.microsoft.com/en-us/library/system.appdomainmanager.appdomainmanager.aspx) 네임스페이스의 구조체에 대한 참조로 바꿉니다.  다음 표는 일반적인 관리되지 않는 형식을 나열한 것입니다.  
  
        |구조체|설명|  
        |---------|--------|  
        |[\<caps:sentence id\="tgt24" sentenceid\="84e2c64f38f78ba3ea5c905ab5a2da27" class\="tgtSentence"\>Boolean\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.boolean\(v=vs.140\).aspx)|부울 값을 나타냅니다.|  
        |[\<caps:sentence id\="tgt26" sentenceid\="40ea57d3ee3c07bf1c102b466e1c3091" class\="tgtSentence"\>Byte\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.byte\(v=vs.140\).aspx)|부호 없는 8비트 정수를 나타냅니다.|  
        |[\<caps:sentence id\="tgt28" sentenceid\="a87deb01c5f539e6bda34829c8ef2368" class\="tgtSentence"\>Char\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.char\(v=vs.140\).aspx)|유니코드 문자를 나타냅니다.|  
        |[\<caps:sentence id\="tgt30" sentenceid\="dfeaaeb4316477bd556ea5e8c3295887" class\="tgtSentence"\>DateTime\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.datetime.datetime.aspx)|일반적으로 날짜와 시간으로 표시된 시간을 나타냅니다.|  
        |[\<caps:sentence id\="tgt32" sentenceid\="bdaa3c20a3e3851599514f7c6be5f62f" class\="tgtSentence"\>10진수\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.decimal\(v=vs.140\).aspx)|10진수를 나타냅니다.|  
        |[\<caps:sentence id\="tgt34" sentenceid\="e8cd7da078a86726031ad64f35f5a6c0" class\="tgtSentence"\>Double\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.double\(v=vs.140\).aspx)|배정밀도 부동 소수점 숫자를 나타냅니다.|  
        |[\<caps:sentence id\="tgt36" sentenceid\="1e0ca5b1252f1f6b1e0ac91be7e7219e" class\="tgtSentence"\>Guid\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.guid\(v=vs.140\).aspx)|GUID\(Globally Unique IDentifier\)를 나타냅니다.|  
        |[\<caps:sentence id\="tgt38" sentenceid\="ce80d5ec65b1d2a2f1049eadc100db23" class\="tgtSentence"\>Int16\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.int16\(v=vs.140\).aspx)|부호 있는 16비트 정수를 나타냅니다.|  
        |[\<caps:sentence id\="tgt40" sentenceid\="0241adbbd83925f051b694d40f02747f" class\="tgtSentence"\>Int32\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.int32\(v=vs.140\).aspx)|부호 있는 32비트 정수를 나타냅니다.|  
        |[\<caps:sentence id\="tgt42" sentenceid\="ff9b3f96d37353c528517bc3656a00a8" class\="tgtSentence"\>Int64\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.int64\(v=vs.140\).aspx)|부호 있는 64비트 정수를 나타냅니다.|  
        |[\<caps:sentence id\="tgt44" sentenceid\="7f1db863563907cf33604ed7fad6b111" class\="tgtSentence"\>IntPtr\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.intptr\(v=vs.140\).aspx)|포인터나 핸들을 나타내는 데 사용되는 플랫폼별 형식입니다.|  
        |[\<caps:sentence id\="tgt46" sentenceid\="943756eb7841efcc43b7cd37d7254c76" class\="tgtSentence"\>SByte\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.byte.aspx)|부호 있는 8비트 정수를 나타냅니다.|  
        |[\<caps:sentence id\="tgt48" sentenceid\="dd5c07036f2975ff4bce568b6511d3bc" class\="tgtSentence"\>Single\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.single.aspx)|단정밀도 부동 소수점 숫자를 나타냅니다.|  
        |[\<caps:sentence id\="tgt50" sentenceid\="90150402997ea9c8dc45cc4d41bb28cb" class\="tgtSentence"\>TimeSpan\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.timespan\(v=vs.140\).aspx)|시간 간격을 나타냅니다.|  
        |[\<caps:sentence id\="tgt52" sentenceid\="a00ef2ef85ff67b7b39339886f19044f" class\="tgtSentence"\>UInt16\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.uint16\(v=vs.140\).aspx)|부호 없는 16비트 정수를 나타냅니다.|  
        |[\<caps:sentence id\="tgt54" sentenceid\="3de84ad0700f2a1571f633d399e1900e" class\="tgtSentence"\>UInt32\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.uint32\(v=vs.140\).aspx)|부호 없는 32비트 정수를 나타냅니다.|  
        |[\<caps:sentence id\="tgt56" sentenceid\="2e8d31865e5d4b9d8611e1b991baed07" class\="tgtSentence"\>UInt64\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.uint64\(v=vs.140\).aspx)|부호 없는 64비트 정수를 나타냅니다.|  
        |[\<caps:sentence id\="tgt58" sentenceid\="92d74abda31865424016b16e2c806a66" class\="tgtSentence"\>UIntPtr\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.uintptr\(v=vs.140\).aspx)|포인터나 핸들을 나타내는 데 사용되는 플랫폼별 형식입니다.|  
        |[\<caps:sentence id\="tgt60" sentenceid\="cab8111fd0b710a336c898e539090e34" class\="tgtSentence"\>Void\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.void\(v=vs.140\).aspx)|값을 반환하지 않는 메서드, 즉 void 반환 형식을 갖는 메서드를 나타냅니다.|