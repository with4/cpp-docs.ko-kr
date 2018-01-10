---
title: pgomgr | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- pgomgr program
- profile-guided optimizations, pgomgr
ms.assetid: 74589126-df18-42c9-8739-26d60e148d6a
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8cbb9a4f8b92a1cd495e1312c1aa8a8f77cefcd3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="pgomgr"></a>pgomgr
.Pgd 파일에 하나 이상의.pgc 파일에서 프로필 데이터를 추가합니다.  
  
## <a name="syntax"></a>구문  
  
```  
pgomgr [options] pgcfiles pgdfile  
```  
  
#### <a name="parameters"></a>매개 변수  
 `options`  
 Pgomgr에 다음 옵션을 지정할 수 있습니다.  
  
 **/help-**pgomgr 사용할 수 있는 옵션이 표시 됩니다 (짧은 /?).  
  
 **/clear-**하면.pgd 파일의 모든 프로필 정보가 지워집니다. .pgc를 지정할 수 없습니다 있을 때 파일 **/clear** 지정 됩니다.  
  
 **/detail**-선형 그래프 진행 정보를 포함 하 여 자세한 통계를 표시 합니다.  
  
 **요약/**-표시 기능별 통계.  
  
 **고유한 /**-와 함께 사용할 경우 **요약/**, 원인 데코레이팅된 함수 이름을 표시 합니다.  기본값, / 고유한는 표시할 데코 레이트 되지 않은 함수 이름에는 사용 되지 않습니다.  
  
 **병합/**[**:***n*]**-**하면 데이터가.pgc 파일이 나.pgd 파일에 추가할 파일입니다.  선택적 매개 변수  *n* , hat 데이터 추가할지를 지정할 수 있습니다  *n*  시간입니다.  예를 들어 시나리오는 일반적으로 6 번 수행할 수, 하는 경우 테스트 실행에서 두 번 수행 추가 하는 것으로 6 번.pgd 파일에 **pgomgr /merge:**합니다.  
  
 `pgcfiles`  
 하나 이상의.pgc 파일 프로필 데이터가.pgd 파일에 병합 합니다. 단일.pgc 파일이 나 여러.pgc 파일을 지정할 수 있습니다. .Pgc 파일을 지정 하지 않으면 pgomgr에서는 해당 파일 이름이.pgd 파일로 같습니다 모든.pgc 파일을 병합 합니다.  
  
 `pgdfile`  
 .Pgd 파일을 병합 하는.pgc 파일 또는 파일의 데이터를 합니다.  
  
## <a name="remarks"></a>설명  
  
> [!NOTE]
>  [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)] 명령 프롬프트에서만 이 도구를 시작할 수 있습니다. 시스템 명령 프롬프트 또는 파일 탐색기에서는 시작할 수 없습니다.  
  
## <a name="example"></a>예  
 다음 예제에서는.pgd 파일의 데이터 프로 파일링 지워졌습니다.  
  
```  
pgomgr /clear myapp.pgd  
```  
  
 다음 예에서 myapp1.pgc에 프로필 데이터는 3 회.pgd 파일에 추가 되었습니다.  
  
```  
pgomgr /merge:3 myapp1.pgc myapp.pgd  
```  
  
 다음 예제에서는 모든 myapp #.pgc 파일에서 프로필 데이터 myapp.pgd 파일에 추가 됩니다.  
  
```  
pgomgr -merge myapp1.pgd  
```  
  
## <a name="see-also"></a>참고 항목  
 [수동 프로필 기반 최적화 도구](../../build/reference/tools-for-manual-profile-guided-optimization.md)