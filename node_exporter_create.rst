Linux
=====================================================================

Windows
=====================================================================
1. インストーラー取得
---------------------------------------------------------------------
* `リリースノート <https://github.com/prometheus-community/windows_exporter/releases>`_ よりインストーラーを取得
* ``msi`` ファイル取得 (CPUは合わせること)

2. インストーラー実行
---------------------------------------------------------------------
* 管理者権限で ``Powershell`` を起動し、以下実行

.. code-block:: powershell

  msiexec.exe /i <path-to-msi-file> --% ENABLED_COLLECTORS=cpu,logical_disk,memory,process,service

.. note::

  * ``path-to-msi-file`` は適宜変更すること
  * 取得対象メトリクスは適宜修正すること
  * コマンド実行後インストールプロンプトが表示されるため、デフォルトで完了させる

3. 起動確認
---------------------------------------------------------------------
* ブラウザにて ``http://localhost:9182/metrics`` を呼び出し、``windows_*`` のメトリクスが表示されればOK
* ``windows_exporter`` サービスが登録されますので、サーバーマネージャーから確認できます

参考資料
=====================================================================
リファレンス
---------------------------------------------------------------------
* `prometheus/node_exporter - GitHub <https://github.com/prometheus/node_exporter>`_
* `prometheus/node_exporter/releases - GitHub <https://github.com/prometheus/node_exporter/releases>`_
* `prometheus-community/windows_exporter - GitHub <https://github.com/prometheus-community/windows_exporter>`_
* `prometheus-community/windows_exporter/releases - GitHub <https://github.com/prometheus-community/windows_exporter/releases>`_