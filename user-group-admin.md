<h1>Why Linux is a Must-Know for DevOps & Cloud Engineers - Part 1: User & Group Administration</h1>

<p>If you’re starting a career in DevOps or Cloud Engineering, there’s one skill you cannot skip — <strong>Linux</strong>. Whether you're deploying servers on AWS, building containers in Kubernetes, or running CI/CD pipelines, Linux is the underlying operating system in most cloud environments.</p>

<p>In this beginner-friendly guide, we’ll cover how to manage <strong>users and groups</strong> in Linux — something every DevOps or System Admin does regularly. This is the first part of a multi-post series that focuses on hands-on Linux skills for cloud professionals.</p>

<hr>

<h2>Understanding Basic Linux Syntax (for Beginners)</h2>

<p>Before we dive into commands, here are some basics to help you understand the syntax you'll see:</p>

<ul>
  <li><code>sudo</code> – “superuser do”. Run commands with admin (root) privileges.</li>
  <li><code>su</code> – “substitute user”. Switch to another user’s session (usually root).</li>
  <li><code>&lt;username&gt;</code> or <code>&lt;groupname&gt;</code> – Replace with actual usernames/groups.</li>
  <li><code>[]</code> – Indicates optional arguments in command syntax.</li>
</ul>

<hr>

<h2>Why Should You Care About Users & Groups?</h2>

<p>Imagine you're managing a server that the whole team uses. If everyone logs in as the same user, it becomes impossible to track who did what. That’s where <strong>user and group management</strong> comes in.</p>

<p>With separate user accounts and well-defined groups, you can:</p>
<ul>
  <li>Give the right people the right level of access</li>
  <li>Control who can read/write/deploy code</li>
  <li>Improve security and accountability</li>
</ul>

<hr>

<h2>User Management Commands</h2>

<h3>1. <code>useradd</code> — Add a new user</h3>
<pre><code>sudo useradd devuser</code></pre>
<p>Adds a new user named <code>devuser</code> with a home directory.</p>
<p><strong>Example:</strong> Add a new teammate named Sam:</p>
<pre><code>sudo useradd sam</code></pre>

<h3>2. <code>passwd</code> — Set or change a user’s password</h3>
<pre><code>sudo passwd sam</code></pre>
<p>Prompts to set a password for user <code>sam</code>.</p>

<h3>3. <code>usermod</code> — Modify user info</h3>
<pre><code>sudo usermod -d /data/devusers/sam sam</code></pre>
<p>Changes Sam’s home directory to a project-specific folder.</p>

<h3>4. <code>userdel</code> — Delete a user</h3>
<pre><code>sudo userdel sam</code></pre>
<p>Removes Sam’s account from the system.</p>
<p>To also remove the home directory:</p>
<pre><code>sudo userdel -r sam</code></pre>

<hr>

<h2>Group Management Commands</h2>

<h3>5. <code>groupadd</code> — Create a group</h3>
<pre><code>sudo groupadd backenddevs</code></pre>
<p>Creates a group for backend developers.</p>

<h3>6. <code>gpasswd</code> — Add/remove users from a group</h3>
<pre><code>sudo gpasswd -a sam devteam</code></pre>
<p>Adds Sam to the devteam group.</p>
<pre><code>sudo gpasswd -d sam devteam</code></pre>
<p>Removes Sam from the group.</p>

<h3>7. <code>groupmod</code> — Rename a group</h3>
<pre><code>sudo groupmod -n platform devops</code></pre>
<p>Renames <code>devops</code> group to <code>platform</code>.</p>

<h3>8. <code>groupdel</code> — Delete a group</h3>
<pre><code>sudo groupdel testers</code></pre>
<p>Deletes the <code>testers</code> group.</p>

<hr>

<h2>Viewing Info & Switching Users</h2>

<h3>9. <code>id</code> — View user/group info</h3>
<pre><code>id sam</code></pre>
<p>Shows Sam’s user ID, group ID, and memberships.</p>

<h3>10. <code>su</code> — Switch user identity</h3>
<pre><code>su - sam</code></pre>
<p>Switches to the <code>sam</code> account.</p>

<h3>11. <code>sudo</code> — Run command as root</h3>
<pre><code>sudo systemctl restart nginx</code></pre>
<p>Restarts NGINX with elevated privileges.</p>

<hr>

<h2>File Ownership & Permissions</h2>

<h3>12. <code>chown</code> — Change file owner and group</h3>
<pre><code>sudo chown sam:devteam app.log</code></pre>
<p>Gives ownership of <code>app.log</code> to Sam and group <code>devteam</code>.</p>

<h3>13. <code>chgrp</code> — Change group only</h3>
<pre><code>sudo chgrp backenddevs config.yaml</code></pre>
<p>Changes the group ownership of <code>config.yaml</code> to <code>backenddevs</code>.</p>

<hr>

<h2>Wrapping Up</h2>

<p>These are the basics of managing users and groups in Linux. Mastering these will make your life easier — whether you're managing SSH access, automating deployments, or just keeping your server secure and organized.</p>

<h2>Coming Up Next…</h2>

<p>In the next part of this series, we’ll dive into <strong>file permissions</strong> — using <code>chmod</code>, <code>umask</code>, and <strong>ACLs</strong> to control access at a deeper level.</p>

<p>Stay tuned and follow <strong>Bytes & Clouds</strong> for more practical DevOps and Linux tutorials!</p>

