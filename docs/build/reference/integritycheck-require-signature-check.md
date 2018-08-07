---
title: -INTEGRITYCHECK (시그니처 확인 필요) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
ms.assetid: 9e738825-2c98-40cd-8ad2-5d0d9c14893e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 997e3f5bb79ee3cbfa95c5762b0d3e998c56f362
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32374247"
---
# <a name="integritycheck-require-signature-check"></a>/INTEGRITYCHECK(시그니처 확인 필요)
로드할 때 이진 이미지의 디지털 서명을 검사 해야 않도록 지정 합니다.  
  
```  
/INTEGRITYCHECK[:NO]  
```  
  
## <a name="remarks"></a>설명  
 기본적으로 **/INTEGRITYCHECK** 꺼져 있습니다.  
  
 **/INTEGRITYCHECK** 집합 옵션-DLL 파일 또는 실행 파일의 PE 헤더에서-windows에서 이미지를 로드 하려면 디지털 서명을 확인 하도록 메모리 관리자에 대 한 플래그입니다. 이 옵션은 특정 Windows 기능으로 로드되는 커널 모드 코드를 구현하는 32비트 및 64비트 DLL에 대해 설정해야 하며, Windows Vista, [!INCLUDE[win7](../../build/includes/win7_md.md)], [!INCLUDE[win8](../../build/reference/includes/win8_md.md)], [!INCLUDE[winsvr08](../../build/reference/includes/winsvr08_md.md)] 및 [!INCLUDE[winserver8](../../build/reference/includes/winserver8_md.md)]의 모든 장치 드라이버에서 권장됩니다. 버전의 Windows Vista 이전 버전의 Windows는이 플래그를 무시합니다. 자세한 내용은 참조 [강제 무결성 서명의 PE (이식 가능) 파일](http://social.technet.microsoft.com/wiki/contents/articles/255.forced-integrity-signing-of-portable-executable-pe-files.aspx)합니다.  
  
### <a name="to-set-this-linker-option-in-visual-studio"></a>Visual Studio에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  확장 된 **구성 속성** 노드.  
  
3.  확장 된 **링커** 노드.  
  
4.  선택 된 **명령줄** 속성 페이지.  
  
5.  **추가 옵션**, 입력 `/INTEGRITYCHECK` 또는 `/INTEGRITYCHECK:NO`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)   
 [강제 무결성 서명의 PE (이식 가능) 파일](http://social.technet.microsoft.com/wiki/contents/articles/255.forced-integrity-signing-of-portable-executable-pe-files.aspx)   
 [커널 모드 코드 연습 서명](http://msdn.microsoft.com/windows/hardware/gg487328.aspx)   
 [Windows 7 및 Windows Server 2008에서 AppInit Dll](http://msdn.microsoft.com/windows/hardware/gg463040.aspx)