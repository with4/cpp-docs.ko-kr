---
title: "pgomgr | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "pgomgr 프로그램"
  - "프로필 기반 최적화, pgomgr"
ms.assetid: 74589126-df18-42c9-8739-26d60e148d6a
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# pgomgr
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

하나 이상의 .pgc 파일에 있는 프로필 데이터를 .pgd 파일에 추가합니다.  
  
## 구문  
  
```  
pgomgr [options] pgcfiles pgdfile  
```  
  
#### 매개 변수  
 `options`  
 pgomgr에는 다음과 같은 옵션을 지정할 수 있습니다.  
  
 **\/help—**사용할 수 있는 pgomgr 옵션을 보여 줍니다. \/?로 짧게 사용할 수 있습니다.  
  
 **\/clear—**.pgd 파일에 있는 프로필 정보를 모두 지웁니다.  **\/clear**가 지정된 경우 .pgc 파일을 지정할 수 없습니다.  
  
 **\/detail**—선형 그래프 진행 정보를 비롯한 자세한 통계를 표시합니다.  
  
 **\/summary**—함수별 통계를 표시합니다.  
  
 **\/unique**—**\/summary**와 함께 사용하면 데코레이팅된 함수 이름이 표시됩니다.  \/unique를 사용하지 않으면 기본적으로 데코레이팅되지 않은 함수 이름이 표시됩니다.  
  
 **\/merge**\[**:***n*\]**—**.pgc 파일에 있는 데이터를 .pgd 파일에 추가합니다.  선택적 매개 변수인 *n*을 사용하면 데이터가 *n*번 추가되도록 지정할 수 있습니다.  예를 들어 일반적으로 여섯 번 실행하는 시나리오의 경우 테스트 실행에서 한 번 실행한 다음 **pgomgr \/merge:6**을 사용하여 .pgd 파일에 여섯 번 추가할 수 있습니다.  
  
 `pgcfiles`  
 .pgd 파일에 병합하려는 프로필 데이터가 있는 한 개 이상의 .pgc 파일입니다.  단일 .pgc 파일이나 여러 .pgc 파일을 지정할 수 있습니다.  .pgc 파일을 지정하지 않으면 pgomgr는 파일 이름이 .pgd 파일과 같은 모든 .pgc 파일을 병합합니다.  
  
 `pgdfile`  
 .pgc 파일에 있는 데이터를 병합할 .pgd 파일입니다.  
  
## 설명  
  
> [!NOTE]
>  이 도구는 [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)] 명령 프롬프트에서만 시작할 수 있습니다.  시스템 명령 프롬프트 또는 파일 탐색기에서는 시작할 수 없습니다.  
  
## 예제  
 다음 예제에서는 .pgd 파일에서 프로필 데이터를 지웁니다.  
  
```  
pgomgr /clear myapp.pgd  
```  
  
 다음 예제에서는 myapp1.pgc에 있는 프로필 데이터가 .pgd 파일에 세 번 추가됩니다.  
  
```  
pgomgr /merge:3 myapp1.pgc myapp.pgd  
```  
  
 다음 예제에서는 모든 myapp\#.pgc 파일에 있는 프로필 데이터가 myapp.pgd 파일에 추가됩니다.  
  
```  
pgomgr -merge myapp1.pgd  
```  
  
## 참고 항목  
 [프로필 기반 최적화 도구](../../build/reference/tools-for-manual-profile-guided-optimization.md)