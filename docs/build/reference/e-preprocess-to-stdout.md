---
title: -E (stdout으로 전처리) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /e
dev_langs:
- C++
helpviewer_keywords:
- -E compiler option [C++]
- /E compiler option [C++]
- preprocessor output, copy to stdout
- preprocessor output
ms.assetid: ddbb1725-d950-4978-ab2f-30a5cd7b778c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3f9105c5c75bc4695d0b00debdff49acf78690b1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32376916"
---
# <a name="e-preprocess-to-stdout"></a>/E(stdout으로 전처리)
C 및 c + + 소스 파일을 전처리 하 고 표준 출력 장치 전처리 파일을 복사 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/E  
```  
  
## <a name="remarks"></a>설명  
 이 프로세스에서는 모든 전처리기 지시문이 실행 되 매크로 확장이 수행 및 주석이 제거 됩니다. 전처리 된 출력에 메모를 유지 하기 위해 사용 하 여는 [(보존 설명 하는 동안 전처리) /C](../../build/reference/c-preserve-comments-during-preprocessing.md) 컴파일러 옵션을 함께 합니다.  
  
 **/E** 추가 `#line` 지시문을 시작과 끝에 포함된 된 파일의 그리고 조건부 컴파일 용 전처리기 지시문에 의해 제거 된 줄에 출력 합니다. 이러한 지시문 전처리 파일의 줄 번호를 다시 지정 합니다. 결과적으로, 처리의 이후 단계 동안 발생 한 오류는 전처리 파일의 줄 보다는 원본 소스 파일의 줄 번호를 참조 하십시오.  
  
 **/E** 옵션은 컴파일을 억제 합니다. 컴파일에 대 한 전처리 파일을 전송 해야 합니다. **/E** 출력 파일이 표시는 **/FA**, **/Fa**, 및 **/Fm** 옵션입니다. 자세한 내용은 참조 [/FA, /Fa (목록 파일)](../../build/reference/fa-fa-listing-file.md) 및 [/Fm (맵 파일 이름)](../../build/reference/fm-name-mapfile.md)합니다.  
  
 표시 하지 않는 `#line` 지시문을 사용 하 여는 [/EP (#line 지시문 없이 stdout로 전처리)](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) 옵션을 사용 합니다.  
  
 전처리 된 출력 대신 파일로 보내도록 `stdout`를 사용 하 여는 [/P (파일 전처리)](../../build/reference/p-preprocess-to-a-file.md) 옵션을 사용 합니다.  
  
 표시 하지 않는 `#line` 지시문과 송신 전처리 된 출력 파일을 사용 하 여 **/P** 및 **/EP** 함께 합니다.  
  
 미리 컴파일된 헤더를 사용할 수 없습니다는 **/E** 옵션입니다.  
  
 별도 파일을 전처리 하는 경우 공간 내보내지 않습니다 토큰 후 note 합니다. 이 수에 잘못 된 프로그램이 발생할 수도 있고 의도 하지 않은 부작용입니다. 다음 프로그램은 성공적으로 컴파일됩니다.  
  
```  
#define m(x) x  
m(int)main( )  
{  
   return 0;  
}  
```  
  
 그러나으로 컴파일하는 경우:  
  
```  
cl -E test.cpp > test2.cpp  
```  
  
 `int main` test2.cpp에서 잘못 됩니다 `intmain`합니다.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  **C/C++** 폴더를 클릭합니다.  
  
3.  **명령줄** 속성 페이지를 클릭합니다.  
  
4.  입력에 컴파일러 옵션은 **추가 옵션**상자입니다.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GeneratePreprocessedFile%2A>을 참조하세요.  
  
## <a name="example"></a>예제  
 다음 명령줄을 실행 하면 `ADD.C`주석을 유지, 추가, `#line` 지시문을 표준 출력 장치에 결과 표시 합니다.  
  
```  
CL /E /C ADD.C  
```  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)