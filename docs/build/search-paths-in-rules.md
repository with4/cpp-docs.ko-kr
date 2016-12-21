---
title: "규칙에서 경로 검색 | Microsoft Docs"
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
  - "NMAKE의 유추 규칙"
  - "규칙, 유추"
  - "NMAKE 유추 규칙으로 경로 검색"
ms.assetid: 38feded6-536d-425d-bf40-fff3173a5506
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 규칙에서 경로 검색
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

```  
{frompath}.fromext{topath}.toext:  
   commands  
```  
  
## 설명  
 유추 규칙은 종속 줄에 지정된 경로가 유추 규칙 경로와 정확히 일치하는 경우에만 종속 줄에 적용됩니다.  종속 파일의 디렉터리는 *frompath*에 지정하고 대상의 디렉터리는 *topath*에 지정합니다. 공백은 사용할 수 없습니다.  각 확장명에 하나의 경로만 지정합니다.  하나의 확장명에 대한 경로를 지정하려면 다른 확장명에 대한 경로가 필요합니다.  현재 디렉터리를 지정하려면 마침표\(.\)나 빈 중괄호\({ }\)를 사용합니다.  매크로를 사용하여 *frompath*와 *topath*를 나타낼 수 있습니다. 이 매크로는 전처리 중에 호출됩니다.  
  
## 예제  
  
### 코드  
  
```  
{dbi\}.cpp{$(ODIR)}.obj::  
        $(CC) $(CFLAGS) $(YUDBI) $<  
  
{ilstore\}.cpp{$(ODIR)}.obj::  
        $(CC) $(CFLAGS) $<  
  
{misc\}.cpp{$(ODIR)}.obj::  
        $(CC) $(CFLAGS) $(YUPDB) $<  
  
{misc\}.c{$(ODIR)}.obj::  
        $(CC) $(CFLAGS) $<  
  
{msf\}.cpp{$(ODIR)}.obj::  
        $(CC) $(CFLAGS) $<  
  
{bsc\}.cpp{$(ODIR)}.obj::  
        $(CC) $(CFLAGS) $(YUPDB) $<  
  
{mre\}.cpp{$(ODIR)}.obj::  
        $(CC) $(CFLAGS) $(YUPDB) $<  
  
{namesrvr\}.cpp{$(ODIR)}.obj::  
        $(CC) $(CFLAGS) $(YUPDB) $<  
  
{src\cvr\}.cpp{$(ODIR)}.obj::  
        $(CC) $(CFLAGS) $<  
```  
  
## 참고 항목  
 [규칙 정의](../build/defining-a-rule.md)