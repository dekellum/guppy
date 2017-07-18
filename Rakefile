# -*- ruby -*-

ROOT_DIR = File.expand_path( '..', __FILE__ )

desc "systemctl enable socket/service"
task :enable do
  sh <<-SH
    systemctl --user enable #{ROOT_DIR}/systemd/guppy.socket
    systemctl --user enable #{ROOT_DIR}/systemd/guppy.service
  SH
end

[ :status, :start, :stop, :disable ].each do |t|
  desc "systemctl #{t} socket/service"
  task t do
    sh <<-SH
      systemctl --user #{t} guppy.{socket,service}
    SH
  end
end

desc "systemctl restart service"
task :restart do
  sh <<-SH
    systemctl --user restart guppy.service
  SH
end
