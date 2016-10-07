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
              <li>Note: On OS X, if you get nvm: command not found after running the install script, your system may not have 
              a [.bash_profile file] where the command is set up. Simply create one with <code>touch ~/.bash_profile</code> 
              and run the install script again.
              </li>
              <li>If the above doesn't fix the problem, open your .bash_profile and add the following line of code: 
              <code>source ~/.bashrc</code>
              </li>
          </ul>
        </ul>
      </li><br>
      <li>I am currently using version 4.0, so to install that version with nvm, you want to run <code style="background-color:#d3d3d3">&nbsp; nvm install 4.0 &nbsp;</code>.
      </li><br>
    </ul>

  <h3><li>Install grunt-cli</li></h3>
    <ul>
      <li>In your terminal, run the following commands:
      <ol>
        <li><code style="background-color:#d3d3d3">&nbsp; sudo npm install &nbsp;</code></li>
        <li><code style="background-color:#d3d3d3">&nbsp; sudo npm install grunt-cli -g &nbsp;</code></li>
        <li><code style="background-color:#d3d3d3">&nbsp; sudo npm install grunt --save-dev &nbsp;</code></li>
      </ol>
      </li><br>
    </ul>

  <h3><li>Clone Outbox</li></h3>
    <ul>
      <li>In your terminal, run the following command: <code style="background-color:#d3d3d3">&nbsp; git clone <a href="https://github.com/Acornsgrow/Outbox.git" target="_blank" data-saferedirecturl="https://www.google.com/url?hl=en&amp;q=https://github.com/Acornsgrow/Outbox.git&amp;source=gmail&amp;ust=1473642155017000&amp;usg=AFQjCNH4JavbGvqePpyRFRAlSWm-wjEaPA">https://github.com/Acornsgrow/<wbr>Outbox.git</a> &nbsp;</code>
      </li><br>
    </ul>

  <h3><li>Create a 'secrets.json' file</li></h3>

  <h3><li>Run Outbox</li></h3>
    <ul>
      <li>While inside your Outbox directory run: <code style="background-color:#d3d3d3">&nbsp; grunt serve &nbsp;</code>
      </li><br>
      <li>This should pop up a browser window and display the <span class="il">emails</span> on that branch. If it does not automatically pop up, go ahead and navigate to <code>localhost:4000</code> in a browser window. In the top right corner, you will see a drop down menu of all <span class="il">emails</span> on the branch. Browse through the various <span class="il">emails</span>.</li>
    </ul>

  <h3><li>Let's look at Partials</li></h3>
  <ul>
    <li>
    In your terminal inside the outbox directory, let's checkout the universal partials branch. Run the following command: <code style="background-color:#d3d3d3">&nbsp; git checkout universal_template &nbsp;</code>
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
