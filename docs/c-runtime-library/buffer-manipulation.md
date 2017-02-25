---
title: "버퍼 조작 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.memory"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "버퍼"
  - "버퍼, 조작 루틴"
ms.assetid: 164f4860-ce66-412c-8291-396fbd70f03e
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 버퍼 조작
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

바이트 단위로 메모리 영역을 사용 하려면 이 루틴을 사용 합니다.  
  
### 버퍼 조작 루틴  
  
|루틴|기능|해당 .NET Framework|  
|--------|--------|-----------------------|  
|[\_memccpy](../c-runtime-library/reference/memccpy.md)|주어진 문자 또는 주어진 문자의 수가 복사 될 때 까지 하나의 버퍼에서 다른 버퍼로 문자를 복사합니다.|[System::Buffer::BlockCopy](https://msdn.microsoft.com/en-us/library/system.buffer.blockcopy.aspx), [System::String::Copy](https://msdn.microsoft.com/en-us/library/system.string.copy.aspx)|  
|[memchr, wmemchr](../c-runtime-library/reference/memchr-wmemchr.md)|버퍼에 주어진 문자의 문자를 지정된 수의 내에서 첫 번째 발생에 대한 포인터를 반환합니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[memcmp, wmemcmp](../c-runtime-library/reference/memcmp-wmemcmp.md)|지정한 두 개의 버퍼에서 문자 수를 비교 합니다.|[System::String::Compare](https://msdn.microsoft.com/en-us/library/system.string.compare.aspx), [System::String::Equals](https://msdn.microsoft.com/en-us/library/system.string.equals.aspx)|  
|[memcpy, wmemcpy](../c-runtime-library/reference/memcpy-wmemcpy.md), [memcpy\_s, wmemcpy\_s](../c-runtime-library/reference/memcpy-s-wmemcpy-s.md)|하나 이상의 버퍼에서 지정 된 문자의 개수를 복사합니다.|[System::Buffer::BlockCopy](https://msdn.microsoft.com/en-us/library/system.buffer.blockcopy.aspx), [System::String::Copy](https://msdn.microsoft.com/en-us/library/system.string.copy.aspx)|  
|[\_memicmp, \_memicmp\_l](../c-runtime-library/reference/memicmp-memicmp-l.md)|지정 된 문자의 개수를 대\/소문자에 관계 없이 두 개의 버퍼에서 비교합니다.|[System::String::Compare](https://msdn.microsoft.com/en-us/library/system.string.compare.aspx), [System::String::Equals](https://msdn.microsoft.com/en-us/library/system.string.equals.aspx)|  
|[memmove, wmemmove](../c-runtime-library/reference/memmove-wmemmove.md),[memmove\_s, wmemmove\_s](../c-runtime-library/reference/memmove-s-wmemmove-s.md)|하나 이상의 버퍼에서 지정 된 문자의 개수를 복사합니다.|[\<caps:sentence id\="tgt21" sentenceid\="3833f84fafc5c85a0cac972319a7142c" class\="tgtSentence"\>System::Buffer::BlockCopy\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.buffer.blockcopy.aspx)|  
|[memset, wmemset](../c-runtime-library/reference/memset-wmemset.md)|주어진 문자를 버퍼에서 바이트의 개수를 지정하기 위해 사용합니다.|[\<caps:sentence id\="tgt23" sentenceid\="b681ccb0db940e3c31a14bf4b7e7aaf8" class\="tgtSentence"\>System::Buffer::SetByte\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.buffer.setbyte.aspx)|  
|[\_swab](../c-runtime-library/reference/swab.md)|데이터의 바이트를 교체하고 지정된 위치에 저장합니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
  
 소스와 대상 영역이 겹칠 떄, 오직 `memmove` 만 전체 소스를 제대로 복사하기 위해 생성됩니다.  
  
## 참고 항목  
 [범주별 런타임 루틴](../c-runtime-library/run-time-routines-by-category.md)