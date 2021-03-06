---
title: "C++ のセキュリティのベスト プラクティス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- securitybestpracticesVC
dev_langs:
- C++
helpviewer_keywords:
- Visual C++, security
- security [C++]
- security [C++], best practices
ms.assetid: 86acaccf-cdb4-4517-bd58-553618e3ec42
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0f1474f44b81a95c119a405dda8a91db62a08417
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2018
---
# <a name="security-best-practices-for-c"></a>C++ のセキュリティ推奨事項
ここでは、セキュリティ ツールおよびセキュリティ対策について説明します。 これらを使用しても、アプリケーションを攻撃から完全に防御できるわけではありませんが、攻撃が成功する可能性を低減できます。  
  
## <a name="visual-c-security-features"></a>Visual C++ セキュリティ機能  
 Visual C++ コンパイラおよびリンカーには、次のセキュリティ機能が組み込まれています。  
  
 [/guard (有効にする制御フロー ガードを)](../build/reference/guard-enable-control-flow-guard.md)  
 コンパイラは、コンパイル時に間接的な呼び出しのターゲットに関する制御フローを分析し、実行時に、ターゲットを確認するコードを挿入します。  
  
 [/GS (バッファー セキュリティ チェック)](../build/reference/gs-buffer-security-check.md)  
 利用される危険性がある関数に、オーバーラン検出コードがコンパイラによって挿入されます。 オーバーランが検出されると、実行が停止します。 このオプションの既定値はオンです。  
  
 [/SAFESEH (安全な例外ハンドラーを持つイメージ)](../build/reference/safeseh-image-has-safe-exception-handlers.md)  
 各例外ハンドラーのアドレスを格納したテーブルが、リンカーによって出力イメージに含められます。 実行時に、オペレーティング システムはこのテーブルを使用して適切な例外ハンドラーのみが実行されるようにします。 これにより、実行時に悪意のある攻撃を受けて例外ハンドラーが実行されることを回避できます。 このオプションの既定値はオフです。  
  
 [/NXCOMPAT](../build/reference/nxcompat.md)、 [/NXCOMPAT (データ実行防止と互換性のある)](../build/reference/nxcompat-compatible-with-data-execution-prevention.md)  
 これらのコンパイラ オプションとリンカー オプションを使用すると、データ実行防止 (DEP: Data Execution Prevention) との互換性を有効にできます。 DEP は、CPU で非コード ページが実行されないようにします。  
  
 [/analyze (コード分析)](../build/reference/analyze-code-analysis.md)  
 このコンパイラ オプションを使用すると、潜在的なセキュリティ上の問題 (バッファー オーバーラン、非初期化メモリ、null ポインターの逆参照、メモリ リークなど) を報告するコード解析がアクティブになります。 このオプションの既定値はオフです。 詳細については、次を参照してください。 [C と C++ の概要のコード分析](/visualstudio/code-quality/code-analysis-for-c-cpp-overview)です。  
  
 [/DYNAMICBASE (使用するアドレス領域のレイアウトのランダム化)](../build/reference/dynamicbase-use-address-space-layout-randomization.md)  
 このリンカー オプションにより、実行開始時にメモリ内の個別の場所で読み込むことができる実行可能イメージをビルドできます。 また、このオプションを使用すると、メモリ内のスタックの位置を予測することが非常に難しくなります。  
  
## <a name="security-enhanced-crt"></a>セキュリティが拡張された CRT  
 C ランタイム ライブラリ (CRT) が強化され、セキュリティ上のリスクをもたらす関数 (チェックが適用されない文字列コピー関数 `strcpy` など) の安全なバージョンが導入されました。 このようなセキュリティが万全ではない以前の関数は推奨されないため、これらの関数を使用すると、コンパイル時に警告が表示されます。 コンパイル時に警告が表示されないようにするのではなく、これらの CRT 関数の安全なバージョンを使用することをお勧めします。 詳細については、「 [Security Features in the CRT](../c-runtime-library/security-features-in-the-crt.md)」を参照してください。  
  
## <a name="safeint-library"></a>SafeInt ライブラリ  
 [SafeInt ライブラリ](../windows/safeint-library.md)により整数オーバーフローおよびアプリケーションは、数学的演算を実行するときに発生する可能性がある利用可能なエラーを防止できます。 `SafeInt`ライブラリが含まれています、 [SafeInt クラス](../windows/safeint-class.md)、 [SafeIntException クラス](../windows/safeintexception-class.md)、およびいくつか[SafeInt 関数](../windows/safeint-functions.md)です。  
  
 `SafeInt` クラスを使用することで、整数オーバーフローおよびゼロ除算による攻撃を防止できます。 型が異なる値の比較を処理するために使用できます。 2 種類のエラー処理ポリシーが用意されています。 `SafeInt` クラスの既定のポリシーは、`SafeIntException` クラス例外をスローして、数値演算を完了できない理由を報告することです。 `SafeInt` クラスの 2 番目のポリシーは、プログラムの実行を停止することです。 カスタム ポリシーも定義できます。  
  
 各 `SafeInt` 関数は、対応する 1 つの数値演算で、攻撃に利用される可能性のあるエラーが発生しないようにします。 種類の異なる 2 つのパラメーターを使用できます。これらを同じ型に変換する必要はありません。 複数の数値演算を保護するには、`SafeInt` クラスを使用します。  
  
## <a name="checked-iterators"></a>チェックを行う反復子  
 チェックを行う反復子は、コンテナー境界を強制します。 既定では、チェックを行う反復子が境界の外側にあると、例外が生成され、プログラムの実行が終了します。 Checked 反復子は、プリプロセッサに割り当てられている値に依存するその他のレベルの応答など、定義 **\_SECURE\_SCL\_スロー**と **\_反復子\_デバッグ\_レベル**です。 位置などで**\_反復子\_デバッグ\_LEVEL = 2**、反復子を提供が可能なを使用して、デバッグ モードで包括的な正確性をチェックをアサートします。 詳細については、次を参照してください。[反復子のチェック](../standard-library/checked-iterators.md)と[\_反復子\_デバッグ\_レベル](../standard-library/iterator-debug-level.md)です。  
  
## <a name="code-analysis-for-managed-code"></a>マネージ コードのコード分析  
 マネージ コードのコード分析は FxCop とも呼ばれ、.NET Framework デザイン ガイドラインに準拠するためにアセンブリをチェックします。 FxCop は各アセンブリ内のコードとメタデータを解析して、次の点に不備がないかどうかを検証します。  
  
-   ライブラリ デザイン  
  
-   ローカリゼーション  
  
-   名前付け規則  
  
-   パフォーマンス  
  
-   セキュリティ  
  
## <a name="windows-application-verifier"></a>Windows アプリケーション検証ツール  
 アプリケーション検証ツール (AppVerifier) は、アプリケーションの互換性、安定性、およびセキュリティ上の問題を特定するのに役立ちます。  
  
 AppVerifier は、アプリケーションがどのようにオペレーティング システムを使用するのかを監視します。 AppVerifier は、アプリケーションの実行中に、ファイル システム、レジストリ、メモリ、および API を監視し、AppVerifier がカバーしない問題については、ソース コードの修正を推奨します。  
  
 AppVerifier は、次の用途で使用できます。  
  
-   一般的なプログラミング上の誤りが原因で発生する潜在的なアプリケーションの互換性エラーがないかどうかをテストします。  
  
-   アプリケーションにメモリ関連の問題がないかどうかを調べます。  
  s
-   アプリケーションの潜在的なセキュリティ上の問題を特定します。  
  
 AppVerifier は、Application Compatibility Toolkit の一部である、[アプリケーションの互換性](http://go.microsoft.com/fwlink/p/?linkid=91277)TechNet web サイトでします。  
  

## <a name="windows-user-accounts"></a>Windows ユーザー アカウント  
 Administrators グループに属する Windows ユーザー アカウントを使用すると、開発者とユーザー (機能拡張により) がセキュリティ上の危険にさらされます。 詳細については、次を参照してください。 [Users グループのメンバーとして実行されている](running-as-a-member-of-the-users-group.md)と[アプリケーションのどのユーザー アカウント制御 (UAC) に影響を与える](how-user-account-control-uac-affects-your-application.md)です。  
  
## <a name="see-also"></a>参照  
 <xref:System.Security>   
 [セキュリティ](/dotnet/standard/security/index)   
 [ユーザー アカウント制御 (UAC: User Account Control) がアプリケーションに与える影響](how-user-account-control-uac-affects-your-application.md)