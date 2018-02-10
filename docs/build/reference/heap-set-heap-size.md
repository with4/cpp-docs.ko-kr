---
title: "-HEAP (힙 크기 설정) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.HeapCommitSize
- /heap
- VC.Project.VCLinkerTool.HeapReserveSize
dev_langs:
- C++
helpviewer_keywords:
- -HEAP linker option
- heap allocation, setting heap size
- /HEAP linker option
- HEAP linker option
ms.assetid: a3f71927-7f1d-492c-9fdb-dfccb1a043da
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5dd4ba44a76fa7881ebee2ec2f472dad8675e2c8
ms.sourcegitcommit: a5916b48541f804a79891ff04e246628b5f9a24a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2018
---
# <a name="heap-set-heap-size"></a>/HEAP(힙 크기 설정)
```  
/HEAP:reserve[,commit]  
```  
  
## <a name="remarks"></a>설명  
 /HEAP 옵션 바이트 단위로 힙의 크기를 설정 합니다. 이 옵션은.exe 파일을 빌드할 하는 경우에 사용 합니다.  
  
 *예약* 인수 가상 메모리의 총 힙 할당을 지정 합니다. 기본 힙 크기는 1MB입니다. 링커는 가장 가까운 4 바이트에 지정된 된 값으로 반올림합니다.  
  
 선택적 `commit` 인수를 한 번에 할당할 실제 메모리 양을 지정 합니다. 커밋된 가상 메모리 공간을 예약 하는 페이징 파일에서 발생 합니다. 더 높은 `commit` 값 때 응용 프로그램에 힙 공간이 더 필요 하지만 메모리 요구 사항 및 시작 시간을 증가 하는 시간을 절약할 수 있습니다.  
  
 지정 된 *예약* 및 `commit` 10 진수 또는 C 언어 표기법의 값입니다.  
  
 에서도이 기능을 사용 하는 모듈 정의 파일을 통해 사용할 [HEAPSIZE](../../build/reference/heapsize.md)합니다.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [Visual c + + 프로젝트 속성 설정](../../ide/working-with-project-properties.md)합니다.  
  
2.  클릭는 **링커** 폴더입니다.  
  
3.  클릭는 **시스템** 속성 페이지.  
  
4.  수정 된 **힙 커밋 크기** 속성입니다.  
  
### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.HeapReserveSize%2A> 및 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.HeapCommitSize%2A>을 참조하십시오.  
  
## <a name="see-also"></a>참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)