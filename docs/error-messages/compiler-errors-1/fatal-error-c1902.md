---
title: "심각한 오류 C1902 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1902
dev_langs:
- C++
helpviewer_keywords:
- C1902
ms.assetid: 2dc066cc-fcb1-4725-8bcb-9f44dd0905b7
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: b551b1a7e0ae03a7de5108a1d114155786972847
ms.openlocfilehash: 79987719614dfa3075f9a9090ca1d97f6546ceb3
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="fatal-error-c1902"></a>심각한 오류 C1902
프로그램 데이터베이스 관리자 일치 하지 않습니다. 설치를 확인 하십시오  
  
프로그램 데이터베이스 파일 (.pdb)을 최신 버전의 mspdb 사용 하 여 만든*XXX*.dll 컴파일러가 시스템에서 찾은 것입니다. 이 오류는 일반적으로 mspdbsrv.exe 또는 mspdbcore.dll이 누락 되거나 서로 다른 버전을 mspdb 나타냅니다*XXX*.dll입니다. (의 *XXX* 는 mspdb에서 자리 표시자*XXX*각 제품 릴리스에.dll 파일 이름 변경 합니다. 예를 들어, Visual Studio 2015의 파일 이름은 mspdb140.dll.)  
  
버전이 일치 하는 mspdbsrv.exe, mspdbcore.dll 및 mspdb 확인*XXX*.dll 시스템에 설치 됩니다. 버전이 일치 하지 않는 대상 플랫폼에 대 한 컴파일러 및 링크 도구를 포함 하는 디렉터리에 복사 하지 않은 것을 확인 합니다. 예를 들어 있습니다 복사 했을 수 있는 파일 설정 하지 않고 명령 프롬프트에서 컴파일러 또는 링크 도구를 호출할 수 있도록는 **경로** 환경 변수 적절 하 게 합니다.
