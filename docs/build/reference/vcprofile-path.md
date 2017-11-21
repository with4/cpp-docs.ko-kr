---
title: VCPROFILE_PATH | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VCPROFILE_PATH
dev_langs: C++
helpviewer_keywords: VCPROFILE_PATH environment variable
ms.assetid: 25217aa4-7e86-4eba-854d-10b3c457e4df
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d5b4a2bbb46e906883f3f0c99c84d3b12cc0f104
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="vcprofilepath"></a>VCPROFILE_PATH
.Pgc 파일을 만들 디렉터리를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
VCPROFILE_PATH=path  
```  
  
#### <a name="parameters"></a>매개 변수  
 `path`  
 디렉터리 경로.pgc 파일이 추가 됩니다.  
  
## <a name="remarks"></a>설명  
 기본적으로 프로 파일링 되 고 바이너리와 동일한 디렉터리에.pgc 파일이 만들어집니다.  그러나 이진 파일의 절대 경로 없는 경우, 이진 작성 된 다른 컴퓨터에서 프로 파일링 시나리오를 실행할 때 대/소문자 수 있으므로, 설정할 수 있습니다 `VCPROFILE_PATH` 존재 하는 경로입니다.  
  
## <a name="example"></a>예제  
  
```  
set VCPROFILE_PATH=c:\  
```  
  
## <a name="see-also"></a>참고 항목  
 [프로필 기반 최적화 환경 변수](../../build/reference/environment-variables-for-profile-guided-optimizations.md)