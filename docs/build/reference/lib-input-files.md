---
title: LIB 입력 파일 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- Lib
dev_langs:
- C++
helpviewer_keywords:
- input files, LIB
ms.assetid: e1236f0d-cd90-446b-b900-f311f456085c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 140a0f1d9ef6fdb3ca5e6d6977804684c88af1fb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="lib-input-files"></a>LIB 입력 파일
LIB에서 필요로 하는 입력된 파일은 다음 표에 나와 있는 것 처럼가 사용 되 고 있는 모드에 따라 달라 집니다.  
  
|모드|입력|  
|----------|-----------|  
|기본값 (빌드 또는 라이브러리를 수정 합니다.)|COFF 개체 (.obj) 파일, COFF 라이브러리 (.lib) 32 비트 개체 모델 (OMF) 개체 (.obj) 파일|  
|/EXTRACT와 멤버 추출|COFF 라이브러리 (.lib)|  
|내보내기 파일 및 가져오기 /def 라이브러리|모듈 정의 (.def) 파일, COFF 개체 (.obj) 파일, COFF 라이브러리 (.lib), 32 비트 OMF 개체 (.obj) 파일|  
  
> [!NOTE]
>  16 비트 버전의 LIB에서 만들어진 OMF 라이브러리는 32 비트 버전의 LIB에 입력으로 사용할 수 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [LIB 개요](../../build/reference/overview-of-lib.md)