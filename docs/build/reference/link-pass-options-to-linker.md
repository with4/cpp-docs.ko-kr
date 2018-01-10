---
title: "-링크 (전달 옵션을 링커로) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /link
dev_langs: C++
helpviewer_keywords:
- /link compiler option [C++]
- pass options to linker
- link compiler option [C++]
- linker [C++], passing options to
- -link compiler option [C++]
- cl.exe compiler [C++], passing options to linker
ms.assetid: 16902a94-c094-4328-841f-3ac94ca04848
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d6732f5a2b144172939e23af4addb37b7605de11
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="link-pass-options-to-linker"></a>/link(옵션을 링커로 전달)
하나 이상의 링커 옵션을 링커에 전달 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/link linkeroptions  
```  
  
## <a name="arguments"></a>인수  
 `linkeroptions`  
 링커 옵션 또는 옵션을 링커로 전달 합니다.  
  
## <a name="remarks"></a>설명  
 **/link** 옵션 및 링커 옵션 파일 이름과 CL 옵션 뒤에 나타나야 합니다. 사이 공백을 않습니다 **/link** 및 `linkeroptions`합니다. 자세한 내용은 참조 [링커 옵션 설정](../../build/reference/setting-linker-options.md)합니다.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  클릭는 **링커** 폴더입니다.  
  
3.  링커 속성 페이지를 클릭 합니다.  
  
4.  하나 이상의 속성을 수정 합니다.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   이 컴파일러 옵션을 프로그래밍 방식으로 변경할 수 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)