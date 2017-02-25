---
title: "인수 액세스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.arguments"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "인수 액세스 매크로[C++]"
  - "가변 길이 인수 목록"
ms.assetid: 7046ae34-a0ec-44f0-815d-3209492a3e19
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 인수 액세스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`va_arg`, `va_end`, 및 `va_start` 매크로는 인수의 숫자가 변수일 때 함수 인수에 대한 액세스를 제공합니다.  이 매크로는 ANSI C 호환성을 위하여 STDARG.H에 정의되며, UNIX 시스템 V와의 호환성을 위하여 VARARGS.H에 정의됩니다.  
  
### 인수 액세스 매크로  
  
|매크로|기능|해당 .NET Framework|  
|---------|--------|-----------------------|  
|[va\_arg](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)|목록에서 인수를 검색|[\<caps:sentence id\="tgt9" sentenceid\="f260effcc218d99ea9ab361455fd493c" class\="tgtSentence"\>System::ParamArrayAttribute 클래스\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.paramarrayattribute.aspx)|  
|[va\_end](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)|포인터를 다시 설정|[\<caps:sentence id\="tgt12" sentenceid\="f260effcc218d99ea9ab361455fd493c" class\="tgtSentence"\>System::ParamArrayAttribute 클래스\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.paramarrayattribute.aspx)|  
|[va\_start](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)|인수 목록의 시작 부분으로 포인터를 설정합니다.|[\<caps:sentence id\="tgt15" sentenceid\="f260effcc218d99ea9ab361455fd493c" class\="tgtSentence"\>System::ParamArrayAttribute 클래스\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.paramarrayattribute.aspx)|  
  
## 참고 항목  
 [범주별 런타임 루틴](../c-runtime-library/run-time-routines-by-category.md)