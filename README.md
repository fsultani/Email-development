# Email-development

## Setup instructions
<ol>
  <h3><li>Install node</li></h3>
    <ul>
      <li>An easy way to do this is to install NVM, which is a Node Version Manager. It can be found at <a href="https://github.com/creationix/nvm" target="_blank" data-saferedirecturl="https://www.google.com/url?hl=en&amp;q=https://github.com/creationix/nvm&amp;source=gmail&amp;ust=1473642155017000&amp;usg=AFQjCNFOVXZ710YV6ScwuFIuN51j238gnA">https://github.com/creationix/nvm</a>.
        <ul>
          <li>Run <code>curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.32.0/install.sh | bash</code> in 
          terminal.
            <ul>
              <li>Note: On OS X, if you get <code>nvm: command not found</code> after running the install script, your system 
              may not have a [.bash_profile file] where the command is set up. Simply create one with <code>touch 
              ~/.bash_profile</code>, and run the install script again.
              </li>
              <li>If the above doesn't fix the problem, open your .bash_profile (type <code>open ~/.bash_profile</code> in 
                terminal), and add the following line of code: <code>source ~/.bashrc</code>.
              </li>
              <li>Close terminal, then reopen it.  Verify that nvm has been installed with <code>command -v nvm</code>.
              </li>
            </ul>
           </li>
           
           <li>
           To download, compile, and install the latest release of node, type <code>nvm install node</code>
           </li>
        </ul>
      </li>
    </ul>

  <h3><li>Install grunt-cli</li></h3>
    <ul>
      <li>In your terminal, run the following commands:
      <ol>
        <li><code style="background-color:#d3d3d3">sudo npm install</code></li>
        <li><code style="background-color:#d3d3d3">sudo npm install grunt-cli -g</code></li>
        <li><code style="background-color:#d3d3d3">sudo npm install grunt --save-dev</code></li>
      </ol>
      </li><br>
    </ul>

  <h3><li>Clone Outbox</li></h3>
    <ul>
      <li>In your terminal, run the following command: <code style="background-color:#d3d3d3">git clone https://github.com/Acornsgrow/Outbox.git</code>
      </li><br>
    </ul>

  <h3><li>Create a 'secrets.json' file</li></h3>

  <h3><li>Run Outbox</li></h3>
    <ul>
      <li>While inside your Outbox directory run: <code style="background-color:#d3d3d3">grunt serve</code>
      </li><br>
      <li>This should pop up a browser window and display the <span class="il">emails</span> on that branch. If it does not automatically pop up, go ahead and navigate to <code>localhost:4000</code> in a browser window. In the top right corner, you will see a drop down menu of all <span class="il">emails</span> on the branch. Browse through the various <span class="il">emails</span>.</li>
    </ul>

  <h3><li>Let's look at Partials</li></h3>
  <ul>
    <li>
    In your terminal inside the outbox directory, let's checkout the universal partials branch. Run the following command: <code style="background-color:#d3d3d3">git checkout universal_template</code>
    </li><br>
    <li>This is the branch that holds the partials that were all designed for the nurture 3.0 campaign.</li><br>
  </ul>
  
  <h3><li>Checkout Handlebars</li></h3>
  <ul>
    <li>
      Now is a good time to familiarize yourself with handlebars since that is what we use for templating in <span class="il">emails</span>: 
      <a href="http://handlebarsjs.com/" target="_blank" data-saferedirecturl="https://www.google.com/url?hl=en&amp;q=http://handlebarsjs.com/&amp;source=gmail&amp;ust=1473642155017000&amp;usg=AFQjCNHBqDZy71x_MD13vjkKzaW_LkrbGw">http://handlebarsjs.com/</a>
    </li>
  </ul>

  <h3><li>Look at, and play with, the <span class="il">emails</span></li></h3>
  <ul>
    <li>
      We build our <span class="il">emails</span> using partials and piece them together using handlebars. You can find the partials inside your outbox directory at <code>/src/partials/components</code>.  The files all end in <code>.hbs</code>, which is the handlebars file extension. Take a look inside the various files to see how the partials are constructed. These partials are styled in corresponding <code>.scss</code> files located in <code>/src/css/scss/components</code>.
    </li><br>
    <li>
      Now checkout the files located inside <code>/src/<span class="il">emails</span></code>.  These files are where the partials are actually pieced together to build the <span class="il">email</span>. <code>test.hbs</code> is the file I use for testing all of my brand new partials and seeing them amongst other completed partials.  In this file you can see it simply calls to other handlebar files and stacks them on top of one another.  Play around in here for a while. Make changes to the handlebar calls to see what happens. Add new instances of partials, take some away, check out how it affects the <span class="il">emails</span> in your browser when you edit the variables being passed into the partials. You can take this a step further and alter the code in the partials themselves to see how it reflects in the <span class="il">email</span> in the browser. Feel free to even create your own partials and make calls to them!
    </li><br>
  </ul>
</ol>

## Usage
<ol>
  <li><code>cd</code> into the directory you want work in.
  <li>Make sure your <code>secrets.json</code> file is in that directory.
  <li>Ensure npm is properly installed, along with grunt.
  <li>Run the following commands for npm and grunt:
    <ul>
      <li>
        <code>sudo npm install</code>
      </li>
      <li>
        <code>sudo npm install grunt-cli -g</code>
      </li>
      <li>
        <code>sudo npm install grunt --save-dev</code>
      </li>
    </ul>
  </li>
</ol>

## Found Money Emails
<ol>
<h3><li>Development</li></h3>
	<ol>
		<li>In terminal, <code>cd</code> into Outbox - found_money_reward</li>
		<li>Modify/update hbs file</li>
		<li>Update the version at the top, in the <code>title</code> tag</li>
	</ol>
<h3><li>Staging</li></h3>
<ol>
	<li>In terminal, run the following commands:
		<ul>
			<li>For 'Coming Soon': <code>python admin-staging.py src/emails/coming-soon-backup.hbs 047fd374-ba74-4dac-9d49-d9b39f5fd44e</code></li>
			<li>For 'Invested': <code>python admin-staging.py src/emails/invested-backup.hbs a9c7f27a-75ae-4857-8b63-3953fcc924f9</code></li>
		</ul>
	</li>
	<li>Go to https://adminstaging.acorns.com/offers/campaigns?locale=en, and select the campaign you’re working on.</li>
	<li>Click "Import Rewards" to upload your csv file.</li>
	<li>The csv file should be this format:
		<ul>
			<li>user_uuid,amount,campaign_id,origination_id,origination_type<br>93baa5e6-2b5d-439b-a074-ee1e7ebfe580,14.30,941c11a8-3c1e-46a1-9be5-269d4f3c48a8,86203,drfizzle
			<li>Only change the campaign_id, and origination_id (you may also change the amount if you want)</li>
		</ul>
	</li>
</ol>
</ol>
