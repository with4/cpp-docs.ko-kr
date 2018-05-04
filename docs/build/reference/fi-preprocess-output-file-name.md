---
title: -Fi (출력 파일 이름 전처리) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /Fi
dev_langs:
- C++
helpviewer_keywords:
- Fi compiler option (C++)
- -Fi compiler option (C++)
- /Fi compiler option (C++)
- preprocessing output files, file name
ms.assetid: 6d0ba983-a8b7-41ec-84f5-b4688ef8efee
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0e7fe5ffbb8a6ccdd5ef02d2cf3feb6b94d48233
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="fi-preprocess-output-file-name"></a>/Fi (출력 파일 이름 전처리)
대상 출력 파일의 이름을 지정는 [/P (파일 전처리)](../../build/reference/p-preprocess-to-a-file.md) 컴파일러 옵션 전처리 된 출력을 씁니다.  
  
## <a name="syntax"></a>구문  
  
```  
/Fipathname  
```  
  
#### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`pathname`|생성 된 이름 및 출력 파일의 경로 **/P** 컴파일러 옵션입니다.|  
  
## <a name="remarks"></a>설명  
 사용 하 여는 **/Fi** 함께에서 컴파일러 옵션은 **/P** 컴파일러 옵션입니다.  
  
 에 대 한 경로 지정 하는 경우는 `pathname` 매개 변수를 소스 파일의 기본 이름 전처리 된 출력 파일의 기본 이름으로 사용 됩니다. `pathname` 매개 변수는 특정 파일 이름 확장명이 필요 하지 않습니다. 그러나 ".i"의 확장 파일 이름 확장명을 지정 하지 않을 경우 사용 됩니다.  
  
## <a name="example"></a>예제  
 다음 명령줄 PROGRAM.cpp 전처리, 주석을 유지, 추가 [#line](../../preprocessor/hash-line-directive-c-cpp.md) 지시문 MYPROCESS.i 파일에 결과 기록 합니다.  
  
```  
CL /P /FiMYPROCESS.I PROGRAM.CPP  
```  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [/P (파일 전처리)](../../build/reference/p-preprocess-to-a-file.md)   
 [경로 이름 지정](../../build/reference/specifying-the-pathname.md)