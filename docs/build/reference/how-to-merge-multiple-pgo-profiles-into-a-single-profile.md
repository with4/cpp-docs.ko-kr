---
title: "방법: 여러 개의 PGO 프로필을 단일 프로필로 병합 | Microsoft Docs"
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
  - "프로필 병합"
  - "프로필 기반 최적화, 프로필 병합"
ms.assetid: aab686b5-59dd-40d1-a04b-5064690f65a6
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 방법: 여러 개의 PGO 프로필을 단일 프로필로 병합
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

PGO\(프로필 기반 최적화\)는 프로파일링된 시나리오를 기반으로 최적화된 이진 파일을 만드는 강력한 도구입니다.  그러나 응용 프로그램에 각기 중요하면서도 서로 구분된 여러 개의 시나리오가 있는 경우 서로 다른 여러 시나리오에서 PGO가 사용할 수 있는 단일 프로필을 만들려면 어떻게 해야 할까요?  Visual Studio에서는 PGO Manager인 Pgomgr.exe가 이 작업을 수행합니다.  
  
 프로필을 병합하는 구문은 다음과 같습니다.  
  
```  
pgomgr /merge[:num] [.pgc_files] .pgd_files  
```  
  
 여기서 `num`은 이 병합에 사용되는 선택적 가중치입니다.  가중치는 일반적으로 다른 시나리오보다 더 중요한 시나리오가 있거나 여러 차례 실행해야 할 시나리오가 있는 경우에 사용됩니다.  
  
> [!NOTE]
>  부실 프로필 데이터는 PGO Manager에 사용할 수 없습니다.  .pgc 파일을 .pgd 파일에 병합하려면 .pgd 파일을 생성한 것과 동일한 링크 호출을 사용하여 만든 실행 파일로 .pgc 파일을 생성해야 합니다.  
  
## 예제  
 이 예제에서 PGO Manager는 pgcFile.pgc를 pgdFile.pgd에 여섯 번 추가합니다.  
  
```  
pgomgr /merge:6 pgcFile.pgc pgdFile.pgd  
```  
  
## 예제  
 이 예제에서 PGO Manager는 pgcFile1.pgc와 pgcFile2.pgc를 pgdFile.pgd에 .pgc 파일당 두 번씩 추가합니다.  
  
```  
pgomgr /merge:2 pgcFile1.pgc pgcFile2.pgc pgdFile.pgd  
```  
  
## 예제  
 .pgc 파일 없이 PGO Manager를 실행하면 .pgd 파일과 이름이 같고 그 이름 뒤에 느낌표\(\!\)와 임의의 문자가 차례로 추가된 모든 .pgc 파일을 로컬 디렉터리에서 검색합니다.  로컬 디렉터리에 test.pgd, test\!1.pgc, test2.pgc 및 test\!hello.pgc 파일이 있는 경우 로컬 디렉터리에서 다음 명령을 실행하면 test\!1.pgc와 test\!hello.pgc가 test.pgd에 병합됩니다.  
  
```  
pgomgr /merge test.pgd  
```  
  
## 참고 항목  
 [프로필 기반 최적화](../../build/reference/profile-guided-optimizations.md)