---
title: -PDBPATH | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /pdbpath
dev_langs: C++
helpviewer_keywords:
- .pdb files, path
- -PDBPATH dumpbin option
- /PDBPATH dumpbin option
- PDBPATH dumpbin option
- PDB files, path
ms.assetid: ccf67dcd-0b23-4250-ad47-06c48acbe82b
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0ccbcedbf9cdd376fa7d9bced5c9d49542cee9f6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="pdbpath"></a>/PDBPATH
```  
/PDBPATH[:VERBOSE] filename  
```  
  
## <a name="remarks"></a>설명  
 다음은 각 문자에 대한 설명입니다.  
  
 *filename*  
 일치 하는.pdb 파일을 찾을 하려는.dll 또는.exe 파일의 이름입니다.  
  
 자세한 정보 표시 (선택 사항)  
 여기서 했습니다.pdb 파일을 찾기 위해 모든 디렉터리를 보고 합니다.  
  
## <a name="remarks"></a>설명  
 /PDBPATH 경로 따라 동일한 디버거는를 검색 하는.pdb 파일에 대 한 보고 있는 경우.pdb 파일에 해당 파일에 지정 하는 컴퓨터에서 검색 됩니다 *filename*합니다.  
  
 Visual Studio 디버거를 사용 하면 되기 때문입니다 디버거가 디버깅 하는 파일의 다른 버전에 대 한.pdb 파일을 사용 하는 문제가 발생할 수 있습니다.  
  
 /PDBPATH는.pdb 파일은 다음 경로 따라 검색 합니다.  
  
-   실행 파일이 있는 위치를 확인 합니다.  
  
-   실행 파일에 작성 된 PDB의 위치를 확인 합니다. 이것이 일반적으로 위치 이미지가 링크 된 시간에입니다.  
  
-   Visual Studio IDE에 구성 된 검색 경로 따라 확인 합니다.  
  
-   _NT_ALT_SYMBOL_PATH 고 _NT_SYMBOL_PATH에서 경로 따라 환경 변수를 확인 합니다.  
  
-   Windows 디렉터리에서 확인 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [DUMPBIN 옵션](../../build/reference/dumpbin-options.md)   
 [/PDBALTPATH (대체 PDB 경로 사용)](../../build/reference/pdbaltpath-use-alternate-pdb-path.md)